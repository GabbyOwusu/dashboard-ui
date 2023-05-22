<template>
  <div
    class="w-[280px] h-[120px] bg-white px-4 py-4 rounded-xl flex flex-col justify-between"
  >
    <div>
      <div class="flex">
        <h1 class="text-sm mr-2">{{ board.leading }}</h1>
        <h1 class="text-sm mb-[1px]">{{ board.title }}</h1>
      </div>
      <h1 class="text-sm text-gray-500">{{ board.description }}</h1>
    </div>

    <ul class="flex">
      <li v-for="avatar in userAvatars" :key="avatar.id" class="-mr-[5px]">
        <Avatar
          borderWidth="1.5"
          :borderColor="avatar.borderColor"
          size="25"
          :avatar="avatar.avatar"
        />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    board: { type: Object, required: true },
    userAvatars: { type: Array },
  },
};
</script>
