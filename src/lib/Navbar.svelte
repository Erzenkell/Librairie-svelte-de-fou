<script>
  import HamburgerMenu from './HamburgerMenu.svelte'

  let menuItems = ['Home', 'About', 'Contact']
  let activeMenuItem = 'Home'
</script>

<main>
  <nav class="container">
    <h2 class="navbar_pseudo">
      <a href="#">Pseudo</a>
    </h2>
    <section class="navbar_navigation">
      <a href="">Home</a>
      <a href="">Thing</a>
      <a href="">Yes</a>
    </section>
    <HamburgerMenu {menuItems} />
  </nav>
</main>

<style>
  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #f5f5f5;
    padding: 0.5rem 1rem;
    border-bottom: 1px solid #e5e5e5;
  }
</style>
