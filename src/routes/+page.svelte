<script>
  export const prerender = true

  let images = [
    { title: 'a', src: '../bg1.jpg' },
    { title: 'b', src: '../bg2.jpg' },
    { title: 'c', src: '../bg3.jpg' },
    { title: 'd', src: '../bg4.jpg' },
    { title: 'e', src: '../bg5.jpg' }
  ]
  import Carousel from '../lib/Carousel.svelte'
  import Todo from '../lib/Todo.svelte'
  import Tabs from '../lib/Tab.svelte'
  import Timer from '../lib/Timer.svelte'
  import List from '../lib/List.svelte'
  import Button from '../lib/Button.svelte'
  import ContactCard from '../lib/ContactCard.svelte'
  import Modal from '../lib/Modal.svelte'
  import Navbar from '../lib/Navbar.svelte'
  import Divider from '../lib/Divider.svelte'
  import Dropdown from '../lib/Dropdown.svelte'

  let schools = ['HETIC', 'EEMI', 'Epitech', 'Etna']
  let toStrong = 'HETIC'

  let tabItems = ['Home', 'Not Home', '???']
  let activeItem = 'Home'

  const triggerTabChange = (event) => {
    activeItem = event.detail
  }

  let showModal = false

  let pseudo = 'MyPseudo'
  let menuItems = ['Home', 'About', 'Contact']
  let burgerItems = ['Home', 'About', 'Contact', 'Blog', 'Careers', 'Support']
</script>

<main>
  <Divider>
    <div slot="dividerContent">Contact Card</div>
  </Divider>
  <ContactCard>
    <span slot="name"> M. Sion </span>

    <span slot="address">
      ICI<br />
      Pas la bas
    </span>
  </ContactCard>

  <Divider>
    <div slot="dividerContent">Modal</div>
  </Divider>

  <button on:click={() => (showModal = true)}> show modal </button>

  {#if showModal}
    <Modal on:close={() => (showModal = false)}>
      <h2 slot="header">Coucou</h2>
      <p>Je suis le text</p>
    </Modal>
  {/if}

  <Divider>
    <div slot="dividerContent">Boutons</div>
  </Divider>

  <Button buttonType="primary">Primary</Button>
  <Button buttonType="secondary">Secondary</Button>
  <Button buttonType="primary" inverse={true}>Inverse Primary</Button>
  <Button buttonType="secondary" inverse={true}>Inverse Secondary</Button>
  <Button flat={true}>Flat</Button>
  <Button disabled={true}>Disabled</Button>

  <Divider>
    <div slot="dividerContent">Tabs</div>
  </Divider>

  <Tabs {tabItems} {activeItem} on:tabChange={triggerTabChange} />
  {#if activeItem === 'Home'}
    <p>Welcome Home</p>
  {:else if activeItem === 'Not Home'}
    <p>Welcome Not Home</p>
  {:else}
    <p>Where are you ?</p>
  {/if}

  <Divider>
    <div slot="dividerContent">List</div>
  </Divider>

  <List {schools} {toStrong} />

  <Divider>
    <div slot="dividerContent">Timer</div>
  </Divider>

  <div class="card">
    <Timer />
  </div>

  <Divider>
    <div slot="dividerContent">Dropdown</div>
  </Divider>

  <Dropdown />

  <Divider>
    <div slot="dividerContent">Carousel de fou</div>
  </Divider>

  <section class="flex flex-col items-center my-10">
    <br />
    <p>
      Carousel simple fait avec Svelte & Tailwind, fonctionnalit?? 'magn??tique',
      peut comprendre n'importe quel nombre de photos.
    </p>
    <br />
    <Carousel {images} />
    <slot />
  </section>

  <Divider>
    <div slot="dividerContent">Todo list de fou</div>
  </Divider>

  <br />
  <p>
    Todo list stylis??e avec Tailwind,ajout et suppression d'??l??ments, checkbox
    de compl??tion, pas d'utilisation de localstorage.
  </p>
  <br />

  <section class="border-solid border-2 border-white-500">
    <Todo />
  </section>

  <Divider>
    <div slot="dividerContent">Navbar</div>
  </Divider>
  <Navbar {pseudo} {menuItems} {burgerItems} />
</main>
