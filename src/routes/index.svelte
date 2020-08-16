<script>

  // Header Items list
  let headerItems = [
    {
      link: "",
      title: "Lorem Ipsum"
    },
    {
      type: "logotype"
    },
    {
      link: "",
      title: "Lorem Ipsum"
    }
  ];
</script>

<!-- Main Layout -->
<main class="w-full h-full relative">

  <!-- Header -->
  <div class="absolute inset-x-0 top-0 w-full py-4 flex justify-center items-center">
    {#each headerItems as item}
      {#if item.type == "logotype"}
        <h1 class="mx-8 font-bold text-xl" style="font-family: Junegull">ideas</h1>
      { :else }
        <a href="{item.link}" class="mx-6 text-gray-700 text-sm">{item.title}</a>
      {/if}
    {/each}
  </div>

  <!-- Hero -->
  <div class="h-screen w-full flex justify-center items-center">
    <!-- Texts -->
    <div class="w-1/3 text-center">
      <h1 class="text-5xl font-semibold text-gray-800">Transform your service into community driven.</h1>
      <p class="text-sm text-gray-700">Community-Driven service is a service that is almost entirely managed by the community. We can help you build such a service by providing one of the most important tools - the user voting service.</p>

      <!-- Buttons -->
      <div class="mt-8 w-full flex justify-center md:px-6 lg:px-16">
        <button class="bg-blue-500 w-full rounded-md font-semibold py-4 text-center text-white shadow-lg">
          Start now
        </button>
      </div>
    
      <!-- Fully free badge -->
      <div class="w-full mt-4">
        <p class="mx-4 text-xs text-gray-600">Totally free</p>
      </div>
    </div>
  </div>

  <!-- @Section: Features -->
  <div class="h-screen w-full flex bg-blue-300 justify-center items-center">
  
  </div>

  <!-- Footer -->
  <div class="w-full flex justify-between px-4 md:px-8 lg:px-12 py-6">
    <!-- Wavees Logotype -->
    <div>
      <h1 style="font-family: Junegull;" class="text-xl">wavees</h1>
      <p class="text-gray-700 text-xs">Company</p>
    </div>

    <!-- Some links -->
    <div class="flex items-center">
      <!-- Small links -->
      <div class="hidden md:block mx-2 text-gray-700 text-xs">
        <a class="mx-4" href="https://wavees.ml">All Services</a>
        <a class="mx-4" href="https://github.com/wavees/tunnels">Source Code</a>
      </div>

      <!-- "Learn more About Company" Button -->
      <div class="hidden lg:block mx-6 text-sm">
        <button class="bg-blue-500 w-full rounded-md font-semibold py-2 px-4 md:px-6 lg:px-8 text-center text-white shadow-lg">
          Learn more about Company
        </button>
      </div>

      <!-- Copyright -->
      <div class="mx-6 text-xs">
        © Wavees Company, 2020
      </div>
    </div>
  </div>
</main>