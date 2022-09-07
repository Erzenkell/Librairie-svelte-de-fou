<script>
  export let schools
  export let toStrong
</script>

<main>
  <ul>
    {#each schools as school}
      {#if school === toStrong}
        <ul><strong>{school}</strong></ul>
      {:else}
        <ul>{school}</ul>
      {/if}
    {/each}
  </ul>
</main>
