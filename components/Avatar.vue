<template>
  <div class="relative">
    <div
      :style="{
        height: `${size}px`,
        width: `${size}px`,
        'border-color': `${borderColor}`,
        'border-width': `${borderWidth}px`,
      }"
      class="rounded-[50%] bg-gray-500 border-solid"
    >
      <img
        v-if="avatar"
        class="rounded-[50%]"
        height="50"
        width="50"
        :src="require(`../assets/images/${avatar}.png`)"
      />
    </div>
    <div
      v-if="showActive"
      :style="{
        'background-color': `${isActive ? '#15803D' : 'grey'}`,
      }"
      class="h-2 w-2 rounded-[50%] absolute bottom-2 right-0"
    ></div>
  </div>
</template>

<script>
export default {
  props: {
    size: { type: String, default: "28" },
    avatar: { type: String },
    borderColor: { type: String, default: "#9CA3AF" },
    borderWidth: { type: String, default: "2.5" },
    showActive: { type: Boolean, defatault: false },
    isActive: { type: Boolean, defatault: false },
  },
};
</script>
