<template>
  <main>
    <button @click="toggle()" class="py-2 flex w-full mt-2">
      <div class="h-5 w-5 flex items-center justify-center rounded-md">
        <img
          :class="isOpen ? 'rotate2' : 'rotate'"
          height="12"
          width="12"
          src="~/assets/images/arrow_down.svg"
        />
      </div>
      <h1 class="ml-2 text-sm text-[#989898]">
        {{ label }}
      </h1>
    </button>
    <div :class="isOpen ? '' : 'closed'" id="body">
      <slot />
    </div>
  </main>
</template>

<script>
export default {
  props: {
    label: { type: String },
  },
  data() {
    return {
      isOpen: true,
    };
  },
  methods: {
    toggle() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style>
.closed {
  display: none;
  /* opacity: 0;
  height: 0px;
  width: 0px;
  transition: opacity height width 400ms ease; */
}
</style>
