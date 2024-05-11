<script>
  import { Toggle } from "flowbite-svelte";

  var settings = {
    System_Settings: {
      "Restore Classic File Explorer": false,
      "Disable My People": false,
      "Enable Long Paths": false,
      "Disable TPM Checks": false,
      "Disable Sensor Services": false,
      "Remove Cast To Device": false,
      "Disable Virtualization Based Security": false,
      "Restore Classic Photo Viewer": false,
    },
    Window_Update_Settings: {
      "Disable Automatic Updates": false,
      "Disable Microsoft Store Updates": false,
      "Disable Insider Services": false,
      "Exclude Drivers from Updates": false,
    },
    Taskbar_Settings: {
      "Align Taskbar to Left": false,
      "Disable Widgets": false,
      "Disable Chat": false,
      "Disable Stickers": false,
    },
    Privacy_Settings: {
      "Disable Telemetry Services": false,
      "Disable Cortana": false,
      "Enhance Privacy": false,
      "Disable Start Menu Ads": false,
      "Disable Edge Telemetry": false,
      "Disable Edge Discover": false,
    },
    Gaming_Settings: {
      "Enable Gaming Mode": false,
      "Disable Xbox Live": false,
      "Enhance Game Bar": false,
    },
    Touch_Settings: {
      "Disable Windows Ink": false,
      "Disable Spell Checking": false,
      "Enhance Cloud Clipboard": false,
    },
    Extra_Settings: {
      "Disable Snap Assist": false,
      "Enable Classic Right-Click Menu": false,
      "Enable Compact Mode in Explorer": false,
      "Disable CoPilot AI": false,
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
    gap: 5px;
  }

  .Privacy__Settings {
    grid-column: 2;
    grid-row: 1;
  }

  .Gaming__Settings {
    grid-column: 2;
    grid-row: 2;
  }

  .Touch__Settings {
    grid-column: 2;
    grid-row: 3;
  }

  .Extra__Settings {
    grid-column: 2;
    grid-row: 4;
  }

  .System__Settings {
    grid-column: 1;
    grid-row: 1;
  }

  .Window__Update__Settings {
    grid-column: 1;
    grid-row: 2;
  }

  .Taskbar__Settings {
    grid-column: 1;
    grid-row: 3;
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
