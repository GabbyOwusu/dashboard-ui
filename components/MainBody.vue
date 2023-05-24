<template>
  <div class="bg-[#F5F5F5] w-[80%] py-10 px-10 overflow-scroll no-scrollbar">
    <div class="flex items-start justify-between">
      <div>
        <p>Hey, Alex 👋🏽</p>
        <p class="text-sm text-gray-500">
          Here's what is happening in your workspace
        </p>
      </div>
      <div class="flex bg-[#EDEDED] pl-3 pr-1 py-1 rounded-lg">
        <input
          class="bg-transparent outline-none"
          type="text"
          placeholder="Search...."
        />
        <div class="h-fit w-fit bg-[#E3E3E3] px-1 py-1 rounded-lg">
          <p class="text-xs text-gray-400">CMD+K</p>
        </div>
      </div>
    </div>

    <section class="bg-white my-5 px-3 py-3 rounded-xl mb-1">
      <p class="mb-3 font-medium">Quick actions</p>
      <div class="flex gap-4">
        <div>
          <TextButton fillColor="#F0FBFB" :colored="true" label="Create view" />
        </div>
        <div>
          <TextButton
            leading="💬"
            fillColor="#F0FBFB"
            :colored="true"
            label="New feedback"
          />
        </div>
        <div>
          <TextButton
            leading="🌱"
            fillColor="#F0FBFB"
            :colored="true"
            label="New initiative"
          />
        </div>
        <div>
          <TextButton
            leading="🎨"
            fillColor="#F0FBFB"
            :colored="true"
            label="New design task"
          />
        </div>
        <div>
          <TextButton
            leading="🐞"
            fillColor="#F0FBFB"
            :colored="true"
            label="New bug"
          />
        </div>
      </div>
    </section>

    <section class="w-full flex flex-col mt-6">
      <div class="flex justify-between mb-3">
        <p class="font-medium">Starred boards</p>
        <img
          height="12"
          width="12"
          src="~/assets/images/plus_icon_grey.svg"
          alt=""
        />
      </div>

      <ul class="flex gap-5 overflow-scroll no-scrollbar">
        <li v-for="board in boards" :key="board.id">
          <MemberCard :board="board" :userAvatars="board.avatars" />
        </li>
      </ul>
    </section>

    <section class="bg-white my-10 px-6 py-4 rounded-xl">
      <p class="mb-4 font-medium">Your team</p>

      <div class="flex">
        <div class="flex flex-col gap-1 items-center mr-8">
          <div
            class="flex items-center justify-center h-[50px] w-[50px] rounded-[50%] bg-gray-200"
          >
            <img
              height="16"
              width="16"
              src="~/assets/images/plus_icon_grey.svg"
              alt=""
            />
          </div>
          <p class="text-sm text-gray-500">Invite new</p>
          <p class="text-sm text-gray-500">Members</p>
        </div>

        <ul class="flex gap-2 overflow-scroll no-scrollbar">
          <li v-for="member in members" :key="member.id">
            <div class="flex w-[100px] gap-1 flex-col items-center">
              <Avatar
                :borderColor="member.borderColor"
                :avatar="member.avatar"
                :showActive="true"
                :isActive="member.isActive"
                size="50"
              >
              </Avatar>
              <p class="text-sm font-medium">{{ member.name }}</p>
              <p v-if="member.isActive" class="text-sm text-gray-500">
                {{ member.status }}
              </p>
              <p v-if="!member.isActive" class="text-sm text-gray-500">
                Offline
              </p>
            </div>
          </li>
        </ul>
      </div>
    </section>

    <section>
      <div class="mb-4 flex gap-6">
        <p class="font-medium">Recently Created</p>
        <div class="flex items-center gap-2">
          <p class="text-sm text-gray-400">All assigness</p>
          <img height="12" width="12" src="~/assets/images/arrow_down.svg" />
        </div>
        <div class="flex items-center gap-2">
          <img height="14" width="14" src="~/assets/images/eye-slash.svg" />
          <p class="text-sm text-gray-400">6 hidden properties</p>
          <img height="12" width="12" src="~/assets/images/arrow_down.svg" />
        </div>
      </div>

      <ul v-for="activity in activities" :key="activity.code">
        <li>
          <ActivityCard :activity="activity" />
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      boards: [
        {
          id: "1",
          leading: "🌼",
          title: "Front-end guys",
          description: "The cool guys board",
          avatars: [
            {
              id: "1",
              avatar: "avatar_1",
              borderColor: "#ADB0B9",
            },
            {
              id: "2",
              avatar: "avatar_2",
              borderColor: "#DADCF5",
            },
            {
              id: "4",
              avatar: "avatar_4",
              borderColor: "#D6FFA7",
            },
            {
              id: "5",
              avatar: "avatar_5",
              borderColor: "#FFD3FF",
            },
          ],
        },
        {
          id: "2",
          leading: "🎨",
          title: "Design",
          description: "The cool guys board",
          avatars: [
            {
              id: "1",
              avatar: "avatar_3",
              borderColor: "#FFD3DD",
            },
            {
              id: "2",
              avatar: "avatar_7",
              borderColor: "#ADB0B9",
            },
            {
              id: "3",
              avatar: "avatar_8",
              borderColor: "#DADCF5",
            },
          ],
        },
        {
          id: "3",
          leading: "🗺️",
          title: "Roadmap",
          description: "Upcoming tasks",
          avatars: [
            {
              id: "1",
              avatar: "avatar_3",
              borderColor: "#FFD3DD",
            },
            {
              id: "2",
              avatar: "avatar_5",
              borderColor: "#FFD3FF",
            },
            {
              id: "3",
              avatar: "avatar_4",
              borderColor: "#D6FFA7",
            },
          ],
        },
      ],
      members: [
        {
          id: "1",
          name: "Ekene",
          status: "Viewing bugs",
          avatar: "avatar_1",
          borderColor: "#ADB0B9",
          isActive: true,
        },
        {
          id: "2",
          name: "Daniel",
          status: "Viewing bugs",
          avatar: "avatar_2",
          borderColor: "#DADCF5",
          isActive: true,
        },
        {
          id: "3",
          name: "Joshua",
          status: "Viewing bugs",
          avatar: "avatar_3",
          borderColor: "#FFD3DD",
          isActive: false,
        },
        {
          id: "4",
          name: "Donnald",
          status: "Viewing bugs",
          avatar: "avatar_4",
          borderColor: "#D6FFA7",
          isActive: true,
        },
        {
          id: "5",
          name: "Tolu",
          status: "Viewing bugs",
          avatar: "avatar_5",
          borderColor: "#FFD3FF",
          isActive: false,
        },
      ],
      activities: [
        {
          code: "CYC-82",
          name: "Improve dark mode",
          team: "Design",
          background: "#EAEFFF",
        },
        {
          code: "CYC-81",
          name: "Improve accesibility and keyboard navigation",
          team: "Front-end",
          background: "#E1F2DF",
        },
        {
          code: "CYC-80",
          name: "Add option to edit document on IOS",
          team: "Mobile",
          background: "#FBECD1",
        },
        {
          code: "CYC-79",
          name: "Improve the UX of the bulk action",
          team: "Product",
          background: "#FBEBF5",
        },
        {
          code: "CYC-78",
          name: "Stay logged-in after closing the browser",
          team: "Back-end",
          background: "#E7DEFC",
        },
      ],
    };
  },
};
</script>

<style scoped>
.input {
  height: 10;
}

::placeholder {
  font-size: 0.8rem;
}
</style>
