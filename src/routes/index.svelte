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
  <div class="min-h-screen py-16 lg:py-0 w-full flex justify-center items-center">
    <!-- Texts -->
    <div class="w-full md:w-1/3 text-center">
      <h1 class="text-3xl lg:text-5xl font-semibold text-gray-800">Transform your service into community driven.</h1>
      <p class="text-xs lg:text-sm text-gray-700">Community-Driven service is a service that is almost entirely managed by the community. We can help you build such a service by providing one of the most important tools - the user voting service.</p>

      <!-- Buttons -->
      <div class="w-full mt-8 flex justify-center md:px-6 lg:px-16">
        <button class="w-1/3 bg-blue-500 lg:w-full rounded-md font-semibold py-4 text-center text-white shadow-lg">
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
  <div style="background: linear-gradient(to bottom, #24c6dc, #514a9d);" class="relative py-40 lg:py-0 min-h-screen w-full flex flex-wrap justify-center items-center">
    <!-- Mini-header -->
    <div class="absolute inset-x-0 top-0 w-full text-center py-6">
      <h1 class="text-3xl text-white font-semibold">Features</h1>
      <p class="text-sm text-gray-100">All the things you can do with this service.</p>
    </div>
    
    <!-- Contents -->

    <!-- 
      @feature Make Polls
     -->
    <div class="mx-4 my-4 w-64 h-64 flex flex-col justify-center items-center text-center bg-white shadow-xl rounded-lg">

        <!-- Emoji -->
        <img style="width: 4.5rem; height: 4.5rem;" src="./icons/ballot-box-with-ballot.png" alt="Ballot Emoji">

        <!-- Texts -->
        <div class="mt-4 px-4 md:px-6">
          <h1 class="text-xl font-semibold text-gray-80">Gather user's ideas</h1>

          <p class="mt-2 text-xs text-gray-700">Give your users the opportunity to offer you any ideas or changes for your services.</p>
        </div>

    </div>

    <!-- 
      @feature Fully customizable
     -->
    <div class="mx-4 my-4 w-64 h-64 flex flex-col justify-center items-center text-center bg-white shadow-xl rounded-lg">
      
      <!-- Emoji -->
      <img style="width: 4.5rem; height: 4.5rem;" src="./icons/hammer-and-wrench.png" alt="Toolbox Emoji">

      <!-- Texts -->
      <div class="mt-4 px-4 md:px-6">
        <h1 class="text-xl font-semibold text-gray-80">Customizable</h1>

        <p class="mt-2 text-xs text-gray-700">You can change absolutely anything: starting from poll layout and ending with all texts, colors and backgrounds.</p>
      </div>
      
    </div>

    <!-- 
      @feature Fully free
     -->
    <div class="mx-4 my-4 w-64 h-64 flex flex-col justify-center items-center text-center bg-white shadow-xl rounded-lg">

        <!-- Emoji -->
        <img style="width: 4.5rem; height: 4.5rem;" src="./icons/money-with-wings.png" alt="Money Emoji">

        <!-- Texts -->
        <div class="mt-4 px-4 md:px-6">
          <h1 class="text-xl font-semibold text-gray-80">Fully free</h1>

          <p class="mt-2 text-xs text-gray-700">And, by the way, we don't have any ads! So, our services are fully free and even without any ads. Isn't this good?</p>
        </div>

    </div>

    <!-- Mini-Footer -->
    <div class="absolute inset-x-0 bottom-0 w-full flex justify-center items-center py-6">
      <div class="text-center">
        <button class="bg-blue-500 px-4 md:px-6 lg:px-8 w-full rounded-md font-semibold py-4 text-center text-white shadow-lg">
          Suggest an feature
        </button>
        
        <p class="mt-4 text-xs text-gray-200">More ideas - better service!</p>
      </div>
    </div>
  </div>

  <!-- Footer -->
  <div class="w-full flex justify-between px-4 md:px-8 lg:px-12 py-6">
    <!-- Wavees Logotype -->
    <div>
      <h1 style="font-family: Junegull;" class="text-base">wavees</h1>
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