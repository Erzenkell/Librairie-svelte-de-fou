<style>
  .loader-sample {
    display: flex;
    flex-direction: row;
  }
</style>

<script>
  import Tabs from './lib/Tab.svelte'
  import Timer from './lib/Timer.svelte'
  import List from './lib/List.svelte'
  import Button from './lib/Button.svelte'
  import ContactCard from './lib/ContactCard.svelte'
  import Modal from './lib/Modal.svelte'
  import Navbar from './lib/Navbar.svelte'
  import Divider from './lib/Divider.svelte'
  import Loader from './lib/Loader.svelte'

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
  <Divider >      
    <div slot="dividerContent">
      Contact Card
    </div>
  </Divider>

  <ContactCard>
    <span slot="name"> M. Sion </span>

    <span slot="address">
      ICI<br />
      Pas la bas
    </span>
  </ContactCard>

  <Divider >      
    <div slot="dividerContent">
      Modal
    </div>
  </Divider>

  <button on:click={() => (showModal = true)}> show modal </button>

  {#if showModal}
    <Modal on:close={() => (showModal = false)}>
      <h2 slot="header">Coucou</h2>
      <p>Je suis le text</p>
    </Modal>
  {/if}

  <Divider >      
    <div slot="dividerContent">
      chépa
    </div>
  </Divider>

  <Button buttonType="primary">Primary</Button>
  <Button buttonType="secondary">Secondary</Button>
  <Button buttonType="primary" inverse={true}>Inverse Primary</Button>
  <Button buttonType="secondary" inverse={true}>Inverse Secondary</Button>
  <Button flat={true}>Flat</Button>
  <Button disabled={true}>Disabled</Button>

  <Divider >      
    <div slot="dividerContent">
      Tabs
    </div>
  </Divider>

  <Tabs {tabItems} {activeItem} on:tabChange={triggerTabChange} />
  {#if activeItem === 'Home'}
    <p>Welcome Home</p>
  {:else if activeItem === 'Not Home'}
    <p>Welcome Not Home</p>
  {:else}
    <p>Where are you ?</p>
  {/if}

  <Divider >      
    <div slot="dividerContent">
      List
    </div>
  </Divider>

  <List {schools} {toStrong} />

  <Divider >      
    <div slot="dividerContent">
      Timer
    </div>
  </Divider>

  <div class="card">
    <Timer />
  </div>

  <Divider >      
    <div slot="dividerContent">
      Loader
    </div>
  </Divider>

  <div class="loader-sample">
    <Loader/>
    <Loader size="small"/>
    <Loader size="large"/>
  </div>
</main>
