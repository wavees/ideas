<script>
  // Import modules
  import { user } from "../../config/stores/user.js";
  import { onMount } from "svelte";

  import { fade } from "svelte/transition";

  // Importing components
  import {
    Avatar
  } from "darkmode-components/src/index";

  // Header Items list
  let headerItems = [
    {
      link: "",
      title: "About service"
    },
    {
      link: "",
      title: "Public Polls"
    },
    {
      link: "",
      title: "Add new Poll"
    }
  ];

  let loaded = false;
  onMount(() => {
    setTimeout(() => {
      loaded = true;
    }, 150);
  });

  let polls = [
  ];
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
      <div class="rounded-lg bg-gray-300 rounded-lg py-1 flex items-center px-4 mx-8">
        <img style="height: 1rem;" src="./icons/face-with-party-horn-and-party-hat.png" alt="Smiley =)">
        <p class="ml-2 text-xs text-gray-800">Open beta</p>
      </div>
    </div>

    <!-- Links (centered) -->
    <div class="hidden md:flex w-full justify-center items-center absolute inset-x-0 py-3">
      {#each headerItems as item}
        <a class="mx-6 text-gray-700 text-xs" href="{item.link}">{item.title}</a>
      {/each}
    </div>

    <!-- Profile -->
    <div class="flex items-center">
      <!-- Notification icon -->
      <img style="height: 1.2rem;" class="mx-2" src="./icons/bell.svg" alt="Bell Icon">

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

  <!-- Contents -->
  <div class="relative w-full flex-grow flex items-center justify-center py-6 flex-wrap bg-gray-100">
    {#each polls as poll}
      <div class="mx-4 my-4 w-64 h-64 flex flex-col justify-center items-center text-center bg-white shadow-xl rounded-lg">

          <!-- Emoji -->
          <img style="width: 4.5rem; height: 4.5rem;" src="./icons/money-with-wings.png" alt="Money Emoji">

          <!-- Texts -->
          <div class="mt-4 px-4 md:px-6">
            <h1 class="text-xl font-semibold text-gray-80">Fully free</h1>

            <p class="mt-2 text-xs text-gray-700">And, by the way, we don't have any ads! So, our services are fully free and even without any ads. Isn't this good?</p>
          </div>

      </div>
    {/each}

    <!-- Add new Poll -->
    <div class="mx-4 my-4 w-64 h-64 flex flex-col justify-center items-center text-center bg-white shadow-xl rounded-lg">

      <!-- Emoji -->
      <img style="width: 4.5rem; height: 4.5rem;" src="./icons/{ polls.length > 0 ? "" : "rocket" }.png" alt="Money Emoji">

      <!-- Texts -->
      <div class="mt-4 px-4 md:px-6">
        {#if polls.length > 0}
          <h1 class="text-xl font-semibold text-gray-80">Add new poll</h1>

          <p class="mt-2 text-xs text-gray-700"></p>  
        { :else }
          <h1 class="text-xl font-semibold text-gray-80">Welcome abroad!</h1>

          <p class="mt-2 text-xs text-gray-700">Let's continue our acquaintance! Create your first public Ideas Poll by clicking on the button below.</p>
        {/if}
      </div>

      <!-- Buttons -->
      <div class="w-full px-4 md:px-6 mt-2">
        <button class="w-full bg-blue-500 rounded-md font-semibold py-1 text-sm text-center text-white shadow-lg">
          Add new Poll
        </button>
      </div>
    </div>
  </div>
</main>