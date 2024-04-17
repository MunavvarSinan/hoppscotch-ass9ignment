<template>
  <div class="bg-white border rounded-xl shadow-2xl sm:flex p-3 max-w-2xl md:max-w-3xl transition-all">
    <div class="flex-shrink-0 relative w-full rounded-xl overflow-hidden sm:max-w-60 md:max-w-xs">
      <img class="w-full h-[180px] min-[480px]:h-full top-0 start-0 object-cover" :src="image" alt="Image Description" />
    </div>
    <div class="flex flex-wrap">
      <div class="p-4 py-10 flex flex-col h-full">
        <div class="flex justify-between mb-1">
          <header>
            <div class="font-caveat text-2xl font-medium text-sky-500">{{ tag }}</div>
            <h1 class="text-3xl font-bold text-slate-900">{{ heading }}</h1>
          </header>
          <button
            class="shrink-0 h-[30px] w-[30px] border border-slate-200 hover:border-slate-300 rounded-full shadow inline-flex items-center justify-center focus-visible:outline-none focus-visible:ring focus-visible:ring-indigo-300 transition-colors duration-150 ease-in-out"
            aria-label="Like">
            <svg class="fill-red-500" xmlns="http://www.w3.org/2000/svg" width="14" height="13">
              <path
                d="M6.985 1.635C5.361.132 2.797.162 1.21 1.7A3.948 3.948 0 0 0 0 4.541a3.948 3.948 0 0 0 1.218 2.836l5.156 4.88a.893.893 0 0 0 1.223 0l5.165-4.886a3.925 3.925 0 0 0 .061-5.663C11.231.126 8.62.094 6.985 1.635Zm4.548 4.53-4.548 4.303-4.54-4.294a2.267 2.267 0 0 1 0-3.275 2.44 2.44 0 0 1 3.376 0c.16.161.293.343.398.541a.915.915 0 0 0 .766.409c.311 0 .6-.154.767-.409.517-.93 1.62-1.401 2.677-1.142 1.057.259 1.797 1.181 1.796 2.238a2.253 2.253 0 0 1-.692 1.63Z" />
            </svg>
          </button>
        </div>
        <p class="mt-1 text-gray-500 dark:text-neutral-400">
          {{ description }}
        </p>
        <div className="text-right pt-2">
          <a
            className="text-md font-medium text-indigo-500 hover:text-indigo-600 focus-visible:outline-none focus-visible:ring focus-visible:ring-indigo-300 transition-colors duration-150 ease-out"
            href="{tab.link}"
            >Read more -&gt;</a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    heading: String,
    tag: String,
    description: String,
    image: String,
  },
};
</script>

<style scoped>
.font-caveat {
  font-family: 'Caveat', cursive;
}
</style>
