<script>
    let dropdownMenu = false;
    export let items = ['Banana', 'Berry', 'Apple', 'Cherry']
    const displayDropdown = () => {
        dropdownMenu = !dropdownMenu;
    }
</script>

<style>
    .dropdown {
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 10px;
        background-color: cornflowerblue;
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
        background-color: cornflowerblue;
        border-radius: 10px;
        width: 150px;
        margin-top: 5px;
        position: absolute;
    }

    .menu > div {
        font-weight: bold;
    }

    .item {
        cursor: pointer;
    }
</style>


<div >
    <div class="dropdown" on:click={displayDropdown}>
        <span>Dropdown</span>
        <img class="arrow" src="src\lib\svg\arrow.svg" alt="">
    </div>

{#if dropdownMenu}
    <div class="menu">
        {#each items as fruit}
            <div class="item">{fruit}</div>
        {/each}
    </div>
{/if}
</div>
    