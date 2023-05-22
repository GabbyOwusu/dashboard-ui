<template>
  <button
    :style="{
      'background-color': `${fillColor}`,
      'padding-left': `${fillColor ? '0.5rem' : ''}`,
      'padding-right': `${fillColor ? '0.6rem' : ''}`,
    }"
    class="py-2 flex hover:bg-[#F0FBFB] rounded-[8px] w-full"
  >
    <h1
      v-if="leading"
      :style="{
        color: `${colored ? '#1DA19F' : '#989898'}`,
      }"
      class="ml-2 text-sm"
    >
      {{ leading }}
    </h1>

    <h1
      :style="{
        color: `${colored ? '#1DA19F' : '#989898'}`,
      }"
      class="ml-2 text-sm"
    >
      {{ label }}
    </h1>
  </button>
</template>

<script lang="ts">
export default {
  props: {
    label: { type: String },
    colored: { type: Boolean, default: false },
    fillColor: { type: String },
    leading: { type: String },
  },
};
</script>
