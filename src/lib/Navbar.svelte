<script>
  import HamburgerMenu from './NavbarDropdown.svelte'

  export let pseudo
  export let menuItems
  export let burgerItems
</script>

<main>
  <nav class="container">
    <h2 class="navbar_pseudo">
      <a href="#">{pseudo}</a>
    </h2>
    <section class="navbar_navigation">
      {#each menuItems as item}
        <a href="">{item}</a>
      {/each}
    </section>
    <HamburgerMenu burgerItems={burgerItems} />
  </nav>
</main>

<style>
  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #1414145f;
    padding: 0.5rem 1rem;
    border-bottom: 1px solid #e5e5e5;
  }
  
  a {
    text-decoration: none;
    color: whitesmoke;
    padding: 0.5rem 1rem;
  }
  </style>
