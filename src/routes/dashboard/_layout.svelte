<script>
  // Importing some stores and 
  // modules.
  import { currentData as data } from "../../config/stores/currentData.js";
  import { user } from "../../config/stores/user.js";

  import socket from "../../network/socket.js";

  import { fade } from "svelte/transition";

  // Importing components
  import {
    Avatar
  } from "darkmode-components/src/index";

  import NetworkStatus from "../../components/NetworkStatus.svelte";
  import ProjectsList from "../../components/Header/ProjectsList.svelte";

  import { onMount } from "svelte";

  onMount(() => {
    if (socket.connected) {
      socket.emit('getData', { type: "organizationsList", token: $user.current.token });
    } else {
      socket.on('connect', () => {
        socket.emit('getData', { type: "organizationsList", token: $user.current.token });
      });
    };

    // Loaded Animation
    setTimeout(() => {
      loaded = true;
    }, 150);
  });

  // Listen for organizationsList event from server.
  socket.on('organizationsList', (object) => {
    console.log("RECEIVED OBJECT");
    console.log(object);
    data.pasteData('organizationsList', object.response);
  });

  // Header Items list
  let headerItems = [
    // {
    //   link: "",
    //   title: "About service"
    // },
    // {
    //   link: "",
    //   title: "Public Polls"
    // },
    {
      link: "",
      title: "Add new Poll"
    }
  ];

  let loaded = false;
</script>

<!-- Main Layout -->
<main class="min-h-screen w-full flex flex-col relative">
  {#if !loaded}
    <div out:fade style="z-index: 2;" class="absolute w-full h-screen bg-white"></div>
  {/if}
  
  <!-- Header -->
  <div class="w-full py-4 flex justify-between px-4 md:px-8 relative bg-white">
    <!-- Logotype -->
    <div class="flex items-center">
      <p class="text-xl text-gray-700">ideas</p>

      <!-- badge -->
      <div class="rounded-lg h-8 bg-gray-300 rounded-lg flex items-center px-4 ml-8 mr-4">
        <img style="height: 1rem;" src="./icons/face-with-party-horn-and-party-hat.png" alt="Smiley =)">
        <p class="ml-2 text-xs text-gray-800">Open beta</p>
      </div>

      <!-- Projects List -->
      <ProjectsList />
    </div>

    <!-- Links (centered) -->
    <div class="hidden md:flex w-full justify-center items-center absolute inset-x-0 py-3">
      {#each headerItems as item}
        <a class="mx-6 text-gray-700 text-xs" href="{item.link}">{item.title}</a>
      {/each}
    </div>

    <!-- Profile -->
    <div class="flex items-center">
      <!-- Network Status icon -->
      <NetworkStatus />

      <!-- #Notification icon
      <img style="height: 1.2rem;" class="mx-2 ml-4" src="./icons/bell.svg" alt="Bell Icon"> -->

      <!-- Profile Icon with Chevron -->
      <div class="flex mx-6 items-center">
        <Avatar type="image" avatar={$user.current.avatar} />
        <!-- Icon -->
        <img style="height: 1.2rem;" class="mx-2" src="./icons/chevron-down.svg" alt="Chevron Down">
      </div>

      <!-- Buttons -->
      <div class="flex items-center">
        <button class="mr-2 bg-blue-500 px-4 rounded-md font-semibold py-1 text-sm text-center text-white shadow-lg">
          Settings
        </button>

        <button class="ml-2 px-4 rounded-md font-semibold py-1 text-sm text-center text-gray-800 shadow-lg">
          Logout
        </button>
      </div>
    </div>
  </div>

  <!-- Site's content -->
  <slot></slot>

</main>