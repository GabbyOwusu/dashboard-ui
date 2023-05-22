<template>
  <button
    :style="{
      'background-color': `${fillColor}`,
      'padding-left': `${fillColor ? '0.5rem' : ''}`,
      'padding-right': `${fillColor ? '0.6rem' : ''}`,
    }"
    class="py-2 flex hover:bg-[#F0FBFB] rounded-[8px] w-full"
  >
    <div
      :style="{
        color: `${colored ? '#F0FBFB' : '#686868'}`,
      }"
      class="h-5 w-5 flex items-center justify-center rounded-md"
    >
      <img
        v-if="leadingImage"
        height="17"
        width="17"
        :src="require(`../assets/images/${leadingImage}.svg`)"
        alt=""
      />
      <img
        v-if="colored && !leadingImage"
        height="12"
        width="12"
        src="~/assets/images/plus_icon.svg"
        alt=""
      />
      <img
        v-if="!colored && !leadingImage"
        height="12"
        width="12"
        src="~/assets/images/plus_icon_grey.svg"
        alt=""
      />
    </div>
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
    leadingImage: { type: String },
  },
};
</script>
