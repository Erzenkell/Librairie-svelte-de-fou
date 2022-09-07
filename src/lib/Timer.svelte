<script>
  let seconds = 0
  let identifier
  let hasStarted = false

  const start = () => {
    if (hasStarted) return

    hasStarted = true
    identifier = setInterval(() => {
      seconds++
    }, 100)
  }

  const pause = () => {
    hasStarted = false
    clearInterval(identifier)
  }

  const reset = () => {
    seconds = 0
    pause()
  }
</script>

<main>
  <p>{seconds / 10}</p>
  <button on:click={start}>Démarrer</button>
  <button on:click={pause}>Pause</button>
  <button on:click={reset}>Reset</button>
</main>
