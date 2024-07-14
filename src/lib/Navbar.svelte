<script>
  import { onMount } from 'svelte';

  let isDarkMode = false;

  // Check the initial mode from localStorage or default to dark mode
  onMount(() => {
    isDarkMode = localStorage.getItem('theme') === 'dark' || !localStorage.getItem('theme');
    document.documentElement.classList.toggle('dark', isDarkMode);
  });

  function toggleDarkMode() {
    isDarkMode = !isDarkMode;
    document.documentElement.classList.toggle('dark', isDarkMode);
    localStorage.setItem('theme', isDarkMode ? 'dark' : 'light');
  }
</script>

<nav class="bg-white dark:bg-gray-900 border-gray-200">
    <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
      <a href="/" class="flex items-center space-x-3 rtl:space-x-reverse">
          <img src="https://tsoc.dev/TSoC_Favicon.svg" class="h-8" alt="TSoC Logo" />
          <span class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white">TSoC Fullstack Application</span>
      </a>
      <button data-collapse-toggle="navbar-default" type="button" class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:focus:ring-gray-700" aria-controls="navbar-default" aria-expanded="false">
          <span class="sr-only">Open main menu</span>
          <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
              <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15"/>
          </svg>
      </button>
      <div class="hidden w-full md:block md:w-auto" id="navbar-default">
        <ul class="font-medium flex flex-col p-4 md:p-0 mt-4 border border-gray-100 rounded-lg bg-gray-50 md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:border-0 md:bg-white dark:bg-gray-800 md:dark:bg-gray-900">
          <li>
            <a href="/" class="block py-2 px-3 text-gray-900 dark:text-white bg-blue-700 rounded md:bg-transparent md:text-blue-700 dark:md:text-blue-500 md:p-0" aria-current="page">Home</a>
          </li>
          <li>
            <a href="/profiles" class="block py-2 px-3 text-gray-900 dark:text-white rounded hover:bg-gray-100 dark:hover:bg-gray-700 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 dark:md:hover:text-blue-500 md:p-0">Profiles</a>
          </li>
          <li>
            <a href="/raw-wallet" class="block py-2 px-3 text-gray-900 dark:text-white rounded hover:bg-gray-100 dark:hover:bg-gray-700 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 dark:md:hover:text-blue-500 md:p-0">Raw Wallet</a>
          </li>
          <li>
            <a href="/cloud-wallet" class="block py-2 px-3 text-gray-900 dark:text-white rounded hover:bg-gray-100 dark:hover:bg-gray-700 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 dark:md:hover:text-blue-500 md:p-0">Cloud Wallet</a>
          </li>
          <li>
            <a href="/bounty" class="block py-2 px-3 text-gray-900 dark:text-white rounded hover:bg-gray-100 dark:hover:bg-gray-700 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 dark:md:hover:text-blue-500 md:p-0">Bounty</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
