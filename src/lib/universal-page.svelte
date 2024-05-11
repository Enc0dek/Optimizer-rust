<script>
  import { Toggle } from "flowbite-svelte";

  var settings = {
    System_Settings: {
      "Disable Fax Services": false,
      "Disable Print Services": false,
      "Disable Compatibility Assistant": false,
      "Disable Sticky Keys": false,
      "Disable Error Reporting": false,
      "Disable SmartScreen": false,
      "Optimize Network": false,
      "Optimize Performance": false,
    },
    Disks_Settings: {
      "Disable System Restore": false,
      "Disable Superfetch": false,
      "Disable Hibernation": false,
      "Disable NTFS Timestamps": false,
      "Disable Search": false,
    },
    Apps_Settings: {
      "Disable Office Telemetry": false,
      "Disable Mozilla Firefox Telemetry": false,
      "Disable Google Chrome Telemetry": false,
      "Disable Nvidia Telemetry": false,
      "Disable Visual Studio Telemetry": false,
    },
    Privacy_Settings: {
      "Disable Telemetry Tasks": false,
      "Disable Media Player Sharing": false,
      "Disable HomeGroup": false,
      "Disable SMBv1 Protocol": false,
      "Disable SMBv2 Protocol": false,
    },
  };
</script>

<div class="wrapper">
  {#each Object.entries(settings) as [type, options]}
    <ul class={type.replaceAll("_", "__")}>
      <label for={type.replaceAll("_", "__")}>{type.replaceAll("_", " ")}</label
      >
      {#each Object.entries(options) as [settingname, value]}
        <li>
          <Toggle color="yellow" checked={value}><p>{settingname}</p></Toggle>
        </li>
      {/each}
    </ul>
  {/each}
</div>

<style>
  .wrapper {
    display: grid;
    grid-template-columns: 500px 500px;
    gap: 10px;
  }

  .Apps__Settings {
    grid-column: 2;
    grid-row: 1;
  }

  .Privacy__Settings {
    grid-column: 2;
    grid-row: 2;
  }

  .System__Settings {
    grid-column: 1;
    grid-row: 1;
  }

  .Disks__Settings {
    grid-column: 1;
    grid-row: 2;
  }

  ul {
    overflow: hidden;
  }

  ul li {
    margin: 10px;
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

