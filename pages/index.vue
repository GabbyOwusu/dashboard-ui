<template>
  <main class="flex">
    <SideBar class="overflow-hidden" />
    <MainBody />
  </main>
</template>

<script>
import MainBody from "~/components/MainBody.vue";
import SideBar from "~/components/SideBar.vue";

export default {
  name: "IndexPage",
  components: { SideBar, MainBody },
};
</script>
