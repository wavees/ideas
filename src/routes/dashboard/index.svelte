<script>
  // Import modules
  import { user } from "../../config/stores/user.js";
  import { onMount } from "svelte";

  import { fade } from "svelte/transition";

  import NetworkStatus from "../../components/NetworkStatus.svelte";

  let polls = [
  ];
</script>

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