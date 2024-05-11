<script>
  import Toolbar from './lib/toolbar.svelte'
  import UniversalPage from './lib/universal-page.svelte';
  import Windows11Page from './lib/windows11-page.svelte';
  import CleanerPage from './lib/cleaner-page.svelte';
  import UWP_Apps from "./lib/uwpApps-page.svelte";
  import StartupPage from "./lib/startup-page.svelte";
  import NetworkPage from "./lib/network-page.svelte";
  import HardwarePage from "./lib/Hardware-page.svelte";
  
  var active_page = 1

  function setActivePage(page) {
    active_page = page;
  }
</script>

<main class="container">
  <Toolbar setActivePage={setActivePage}/>

  {#if active_page == 1}
    <UniversalPage/>
  {/if}
  
  {#if active_page == 2}
    <Windows11Page/>
  {/if}

  {#if active_page == 3}
    <UWP_Apps/>
  {/if}

  {#if active_page == 4}
    <StartupPage/>
  {/if}
  
  {#if active_page == 5}
    <CleanerPage/>
  {/if}

  {#if active_page == 6}
    <NetworkPage/>
  {/if}

  {#if active_page == 7}
    <HardwarePage/>
  {/if}
</main>
