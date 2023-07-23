<script setup>
  let props = defineProps({
    active: Boolean,
    name: String,
    icon: String,
  });
</script>
<template>
  <li
    class="border-r-4"
    :class="{ 'border-primary': active, 'border-transparent': !active }"
  >
    <a
      href="#"
      class="flex justify-end px-4 gap-2"
      :class="{ 'text-gray-700 font-bold': active }"
    >
      <span>{{ props.name }}</span>
      <span class="material-symbols-rounded"> {{ props.icon }} </span>
    </a>
  </li>
</template>
