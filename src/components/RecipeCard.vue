<script setup>
  let props = defineProps({
    name: String,
    image: String,
  });
</script>
<template>
  <div class="card hover:shadow-lg transition ease-out duration-200">
    <img
      :src="`src/assets/img/${props.image}.jpg`"
      alt="stew"
      class="w-full h-32 sm:h-48 object-cover"
    />
    <div class="p-4">
      <span class="font-bold">{{ props.name }}</span>
      <span class="text-gray-500 block text-sm">Recipe by Mario</span>
    </div>
    <div class="badge flex items-center gap-1 shadow">
      <span class="material-symbols-rounded text-lg leading-none">
        schedule
      </span>

      <span>25 mins</span>
    </div>
  </div>
</template>
