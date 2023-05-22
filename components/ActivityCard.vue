<template>
  <div
    class="bg-white my-5 pl-2 pr-4 py-2 rounded-xl justify-between flex items-center"
  >
    <div class="flex items-center">
      <div class="h-fit w-fit bg-gray-100 px-2 py-1 rounded-lg mr-4">
        <p class="text-sm text-gray-400">{{ activity.code }}</p>
      </div>
      <p class="text-sm">{{ activity.name }}</p>
    </div>
    <div class="flex gap-4">
      <div
        :style="{
          'background-color': `${activity.background}`,
        }"
        class="h-fit w-fit bg-[#E7DEFC] px-2 py-1 rounded-lg mr-4"
      >
        <p class="text-sm">{{ activity.team }}</p>
      </div>
      <img height="20" width="20" src="~/assets/images/crown.svg" />
      <img height="20" width="20" src="~/assets/images/message.svg" />
      <img height="20" width="20" src="~/assets/images/user-add.svg" />
      <img height="20" width="20" src="~/assets/images/profile-circle.svg" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    activity: { type: Object },
  },
};
</script>
