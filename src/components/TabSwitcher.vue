<template>
  <div
    role="tablist"
    aria-label="tabs"
    class="relative w-max mx-auto h-12 grid grid-cols-3 items-center px-[3px] rounded-full bg-[#E2E8F0] overflow-hidden shadow-900/20 transition focus:outline-none">
    <div class="absolute indicator h-11 my-auto top-0 bottom-0 left-0 rounded-full bg-[#d2d5e2] shadow-md"></div>
    <button
      v-for="(tab, index) in tabs"
      :key="index"
      role="tab"
      :aria-selected="selectedTab === index + 1"
      :aria-controls="'panel-' + (index + 1)"
      :id="'tab-' + (index + 1)"
      :tabindex="selectedTab === index + 1 ? '0' : '-1'"
      class="relative block h-10 px-6 tab rounded-full focus:outline-none"
      @click="selectTab(index + 1)"
      :class="{
        'bg-white': selectedTab === index + 1, // Background for selected tab
        'text-slate-900': selectedTab === index + 1, // Text color for selected tab
        'text-slate-600': selectedTab !== index + 1, // Text color for unselected tabs
      }">
      <span class="font-normal text-sm" :class="{ 'font-semibold': selectedTab === index + 1 }">{{ tab.heading }}</span>
    </button>
  </div>
</template>

<script setup>
const props = defineProps({
  tabs: Array,
  selectedTab: Number,
});

const emit = defineEmits(['tab-selected']);

const selectTab = (index) => {
  emit('tab-selected', index);
};
</script>
