<script>
  export let burgerItems

  let dropdownMenu = false
  const displayDropdown = () => {
    dropdownMenu = !dropdownMenu
  }
</script>

<div class="flex">
  <div class="dropdown" on:click={displayDropdown}>
    <span>{burgerItems[0]}</span>
    <img class="arrow" src="src\lib\svg\arrow.svg" alt="" />
  </div>

  {#if dropdownMenu}
    <div class="menu">
      {#each burgerItems as item}
        <div class="item">{item}</div>
      {/each}
    </div>
  {/if}
</div>

<style>
  .flex {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }
  .dropdown {
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 10px;
    width: 150px;
    height: 50px;
    cursor: pointer;
  }

  .dropdown > span {
    font-weight: bold;
  }

  .arrow {
    height: 15px;
    padding-left: 15px;
  }

  .menu {
    border-radius: 10px;
    width: 150px;
    margin-top: 5px;
  }

  .menu > div {
    font-weight: bold;
  }

  .item {
    cursor: pointer;
  }
</style>
