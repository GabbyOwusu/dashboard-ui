<template>
  <button
    class="flex w-full px-[0.125rem] py-1 items-center hover:text-gray-500"
  >
    <div class="mr-2" v-if="leading">
      <h1>{{ leading }}</h1>
    </div>
    <div class="flex">
      <h1 class="text-sm">
        {{ label }}
      </h1>
    </div>
  </button>
</template>

<script lang="ts">
export default {
  props: {
    label: { type: String },
    leading: { type: String, required: true },
  },
};
</script>
