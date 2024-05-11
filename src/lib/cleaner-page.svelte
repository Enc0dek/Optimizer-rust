<script>
  import { Checkbox } from "flowbite-svelte";
  import { Button } from 'flowbite-svelte';
  import { FileSearchOutline, FileCheckOutline, ArrowUpFromBracketOutline } from 'flowbite-svelte-icons';

  var settings = {
    Windows: {
      "Temp Files": false,
      "BSOD minidumps": false,
      "Error reports": false,
      "Empty Recycle Bin": false,
    },

    Google_Chrome: {
      Cache: false,
      Cookies: false,
      History: false,
      Session: false,
      Passwords: false,
    },

    Mozilla_Firefox: {
      Cache: false,
      Cookies: false,
      History: false,
    },

    Microsoft_Edge: {
      Cache: false,
      Cookies: false,
      History: false,
      Session: false,
    },

    Brave_Browser: {
      Cache: false,
      Cookies: false,
      History: false,
      Session: false,
      Passwords: false,
    },

    Internet_Explorer: {
      Cache: false,
    },
  };

  var files = { "src-tauri/build.rs": false };
</script>

<div class="wrapper">
  <div class="select__files">
    {#each Object.entries(settings) as [type, options]}
      <ul class={type.replaceAll("_", "__")}>
        <label for={type.replaceAll("_", "__")}
          >{type.replaceAll("_", " ")}</label
        >
        {#each Object.entries(options) as [settingname, value]}
          <li>
            <Checkbox color="yellow" checked={value}
              ><p>{settingname}</p></Checkbox
            >
          </li>
        {/each}
      </ul>
    {/each}
  </div>

  <div class="files__list">
    <ul>
      {#each Object.entries(files) as [file, value]}
        <li>
          <Checkbox color="yellow" checked={value}>
            <span style="color: blue;">{file}</span>
          </Checkbox>
        </li>
      {/each}
    </ul>
  </div>

  <div class="files__Control">
    <p>Maximum size to be freed</p>
    <br>
    <p>1gb</p>

    <Button color="yellow">
      <FileSearchOutline/> <p>Analyze</p>
    </Button>

    <Button color="yellow">
      <FileCheckOutline/> <p>Clean</p>
    </Button>

    <Button color="yellow">
      <ArrowUpFromBracketOutline/> <p>Cleanmgr ...</p>
    </Button>
  </div>
</div>

<style>
  .wrapper {
    margin: 0;
    padding: 0;
    display: flex;
    float: left;
    margin-top: -10px;
  }

  .select__files {
    background-color: red;
    width: 250px;
  }

  .files__list {
    background-color: green;
    width: 100%;
  }
  ul {
    list-style-type: none;
    margin: auto;
    padding: 0;
  }
  ul li {
    margin: 6px;
    overflow: hidden;
    list-style-type: none;
  }

  label {
    text-decoration: underline;
  }

  p {
    color: white;
    font-weight: bold;
  }

  p:hover {
    cursor: pointer;
    text-decoration: underline;
  }
</style>
