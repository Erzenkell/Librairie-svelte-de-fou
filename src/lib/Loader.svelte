<style>
    .loader {
  --loading-color: white;
  --loading-size: 2vh;
  --loading-size-small: 3vh;
  --loading-size-large: 4vh;
  position: relative;
  box-sizing: border-box;
  animation: blink 1s infinite;
  animation-delay: 250ms;
  margin-left: 10vw;
  opacity: 0%;
  margin-bottom: 1vh;
}

.loader,
.loader::before,
.loader::after {
  width: calc(var(--loading-size) / 2);
  height: calc(var(--loading-size) / 2);
  border-radius: var(--fluid-6);
  background-color: var(--loading-color);
}

.loader-small,
.loader-small::before,
.loader-small::after {
  width: calc(var(--loading-size-small) / 2);
  height: calc(var(--loading-size-small) / 2);
}

.loader-large,
.loader-large::before,
.loader-large::after {
  width: calc(var(--loading-size-large) / 2);
  height: calc(var(--loading-size-large) / 2);
  border-radius: var(--fluid-8);
}

.loader::before,
.loader::after {
  content: "";
  display: inline-block;
  position: absolute;
  top: 0;
  animation: blink 1s infinite;
}

.loader::before {
  left: calc(-1 * var(--loading-size));
  animation-delay: 0s;
}

.loader::after {
  left: var(--loading-size);
  animation-delay: 500ms;
}

.loader-small::before {
  left: calc(-1 * var(--loading-size-small));
}

.loader-small::after {
  left: var(--loading-size-small);
}

.loader-large::before {
  left: calc(-1 * var(--loading-size-large));
  animation-delay: 0s;
}

.loader-large::after {
  left: var(--loading-size-large);
}

.loader[aria-busy="true"] {
  opacity: 100%;
}

@keyframes blink {
  50% {
    background-color: transparent;
  }
}

@media (prefers-reduced-motion), (update: slow) {
  .loader,
  .loader::before,
  .loader::after {
    transition-duration: 0.001ms !important;
  }
}
</style>

<script>
  export let size = "";
  export let loaderClasses = ["loader", size ? `loader-${size}` : ""]
    .filter((loaderClass) => loaderClass)
    .join(" ");
</script>

<div class={loaderClasses} role="status" aria-live="polite" aria-busy="true"></div>