<script>
  // Importing components and modules
  import { currentData as data } from "../../config/stores/currentData.js";
  import socket from "../../network/socket.js";

  import Popover from "svelte-popover";
</script>

<!-- Main Layout -->
<Popover>
  <button class="rounded-lg h-8 hover:bg-gray-300 rounded-lg flex items-center px-4" slot="target">
    <p class="ml-2 text-xs text-gray-800">{!$data.organizations.loaded ? "Loading..." : $data.organizations.list[0].name}</p>

    <!-- Chevron -->
    <img style="height: 1rem;" class="ml-2" src="./icons/chevron-down.svg" alt="Chevron Down">
  </button>
</Popover>