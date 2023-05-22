<template>
  <button
    class="flex w-full items-center px-1 py-1 rounded-[8px] hover:bg-[#F0FBFB]"
    :style="{
      background: `${isActive ? '#1DA19F' : ''}`,
    }"
  >
    <div class="mr-2" v-if="leading">
      <img
        v-if="!isActive"
        :src="require(`../assets/images/${leading}.svg`)"
        height="16"
        width="16"
      />
      <img
        :src="require(`../assets/images/${leading}_active.svg`)"
        height="16"
        width="16"
        v-if="isActive"
      />
    </div>
    <div class="flex">
      <h1
        :style="{
          color: `${isActive ? 'white' : '#AEAEAE'}`,
        }"
        class="text-sm"
      >
        {{ label }}
      </h1>
    </div>
  </button>
</template>

<script lang="ts">
export default {
  props: {
    label: { type: String },
    isActive: { type: Boolean, default: false },
    leading: { type: String, required: true },
  },
};
</script>
