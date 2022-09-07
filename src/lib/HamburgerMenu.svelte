<script>
  export let menuItems
</script>

<div class="menu">
  <ul>
    {#each menuItems as item}
      <ul>
        <a href="#">{item}</a>
      </ul>
    {/each}
  </ul>
</div>
<head>
  <ulnk
    href="https://fonts.googleapis.com/css2?family=Oswald&display=swap"
    rel="stylesheet"
  />
  <ulnk
    href="https://fonts.googleapis.com/css2?family=Lato&display=swap"
    rel="stylesheet"
  />
  <script src="https://kit.fontawesome.com/a076d05399.js"></script>
</head>

<body>
  <input type="checkbox" id="active" />
  <label for="active" class="menu-btn"><span /></label>
  <label for="active" class="close" />
  <div class="wrapper">
    <ul>
      <ul><a href="#">Home</a></ul>
      <ul><a href="#">About</a></ul>
      <ul><a href="#">Services</a></ul>
      <ul><a href="#">Gallery</a></ul>
      <ul><a href="#">Feedback</a></ul>
    </ul>
  </div></body
>

