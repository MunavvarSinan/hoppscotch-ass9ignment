<template>
  <div class="h-dvh flex justify-center items-center flex-col space-y-5">
    <TabSwitcher :tabs="cardData.tabs" :selectedTab="cardData.selectedTab" @tab-selected="handleTabSelected" />
    <div class="transition duration-150 ease-linear opacity">
      <div v-for="card in filteredCards" :key="card.title">
        <Card :heading="card.heading" :tag="card.tag" :description="card.description" :image="card.image" />
      </div>
    </div>
  </div>
</template>

<script setup>
import TabSwitcher from '@/components/TabSwitcher.vue';
import Card from '@/components/Card.vue';
import Tab1Image from '@/assets/tabs-image-01.webp';
import Tab2Image from '@/assets/tabs-image-02.webp';
import Tab3Image from '@/assets/tabs-image-03.webp';
import { reactive, computed } from 'vue';

const cardData = reactive({
  selectedTab: 1,
  tabs: [
    {
      heading: 'Lassen Peak',
      tag: 'Mountain',
      description: 'It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.',
      image: Tab1Image,
    },
    {
      heading: 'Mount Shasta',
      tag: 'Mountain',
      description: 'It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.',
      image: Tab2Image,
    },

    {
      heading: 'Eureka Peak',
      tag: 'Mountain',
      description: 'It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout.',
      image: Tab3Image,
    },
  ],
});

const handleTabSelected = (index) => {
  cardData.selectedTab = index;
};
const filteredCards = computed(() => {
  const selectedIndex = cardData.selectedTab - 1;
  return selectedIndex >= 0 ? [cardData.tabs[selectedIndex]] : [];
});
</script>
