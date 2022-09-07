<script>
  import Tabs from './lib/Tab.svelte'
  import Timer from './lib/Timer.svelte'
  import List from './lib/List.svelte'
  import Button from './lib/Button.svelte'
  import ContactCard from './lib/ContactCard.svelte'
  import Modal from './lib/Modal.svelte'
  import Navbar from './lib/Navbar.svelte'

  let schools = ['HETIC', 'EEMI', 'Epitech', 'Etna']
  let toStrong = 'HETIC'

  let tabItems = ['Home', 'Not Home', '???']
  let activeItem = 'Home'

  const triggerTabChange = (event) => {
    activeItem = event.detail
  }

  let showModal = false
  let big = false
</script>

<main>
  <!-- Navbar -> WORK IN PROGRESS -->
  <!-- <Navbar /> -->

  <ContactCard>
    <span slot="name"> M. Sion </span>

    <span slot="address">
      ICI<br />
      Pas la bas
    </span>
  </ContactCard>
  <button on:click={() => (showModal = true)}> show modal </button>

  {#if showModal}
    <Modal on:close={() => (showModal = false)}>
      <h2 slot="header">Coucou</h2>
      <p>Je suis le text</p>
    </Modal>
  {/if}

  <Button buttonType="primary">Primary</Button>
  <Button buttonType="secondary">Secondary</Button>
  <Button buttonType="primary" inverse={true}>Inverse Primary</Button>
  <Button buttonType="secondary" inverse={true}>Inverse Secondary</Button>
  <Button flat={true}>Flat</Button>
  <Button disabled={true}>Disabled</Button>

  <Tabs {tabItems} {activeItem} on:tabChange={triggerTabChange} />
  {#if activeItem === 'Home'}
    <p>Welcome Home</p>
  {:else if activeItem === 'Not Home'}
    <p>Welcome Not Home</p>
  {:else}
    <p>Where are you ?</p>
  {/if}

  <List {schools} {toStrong} />

  <div class="card">
    <Timer />
  </div>
</main>
