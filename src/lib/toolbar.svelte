<script>
  export let setActivePage;

  function ChangePage(page) {
    setActivePage(page);
  }
</script>

<div>
  <nav class="nav__horizontal">
    <ul>
      <li><button on:click={() => ChangePage(1)}>Universal</button></li>
      <li><button on:click={() => ChangePage(2)}>Windows 11</button></li>
      <li><button on:click={() => ChangePage(3)}>UWP Apps</button></li>
      <li><button on:click={() => ChangePage(4)}>Startup</button></li>
      <li><button on:click={() => ChangePage(5)}>Cleaner</button></li>
      <li><button on:click={() => ChangePage(6)}>Network</button></li>
      <li><button on:click={() => ChangePage(7)}>Hardware</button></li>
    </ul>
  </nav>
</div>

<style>
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }

  li {
    float: left;
  }

  .nav__horizontal {
    background-color: rgb(61, 61, 61);
    display: flex;
    width: 100%;
    overflow: hidden;
    margin-bottom: 10px;
  }

  nav button {
    background-color: transparent;
    border: none;
    font-size: 18px;
    float: left;
    color: white;
    text-align: center;
    padding: 14px 20px;
    text-decoration: none;
  }

  button:hover {
    background-color: rgb(183, 0, 255);
  }
</style>
