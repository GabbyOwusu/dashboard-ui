<template>
  <nav
    class="w-[20%] h-[100vh] py-4 px-4 flex flex-col justify-between overflow-hidden"
  >
    <div>
      <div class="mb-4 flex items-center justify-between">
        <div class="flex items-center">
          <div class="h-4 w-4 bg-slate-400 mr-2" />
          <h1 class="font-medium">Cube</h1>
        </div>
        <div class="flex items-center">
          <img
            class="mr-2"
            height="22"
            width="22"
            src="../assets/images/notification_bell.svg"
            alt="notification_icon"
          />
          <Avatar avatar="avatar_1" />
        </div>
      </div>

      <SideBarItem leading="home" label="Home" :isActive="true" />
      <SideBarItem leading="inbox" label="Inbox" />
      <SideBarItem leading="search" label="Search" />
      <TextIconButton class="mb-5" label="New feedback" :colored="true" />

      <Accordion class="mb-4" label="Main boards">
        <AccordionItem leading="🗺️" label="Roadmap" />
        <AccordionItem class="mb-1" leading="📝" label="Release notes" />
        <TextIconButton label="Add New" />
      </Accordion>

      <Accordion class="mb-4" label="Design boards">
        <AccordionItem leading="🎨" label="Design system" />
        <AccordionItem leading="🌸" label="Cube design team" />
        <AccordionItem class="mb-1" leading="🚀" label="Cube 2.0" />
        <TextIconButton label="Add New" />
      </Accordion>

      <Accordion class="mb-4" label="Developer">
        <AccordionItem leading="🎨" label="Front-end" />
        <AccordionItem leading="🌸" label="Back-end" />
        <AccordionItem leading="🐞" label="Bugs" />
        <TextIconButton label="Add New" />
      </Accordion>
    </div>

    <div>
      <TextIconButton leadingImage="book" label="Learning center" />
      <TextIconButton leadingImage="info-circle" label="Contact support" />
      <TextIconButton leadingImage="plus_icon_grey" label="Invite new member" />
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isClosed: true,
    };
  },
  methods: {
    toggle() {
      this.isClosed = !this.isClosed;
    },
  },
};
</script>
