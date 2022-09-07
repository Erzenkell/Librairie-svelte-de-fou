<style>
    .divider {
    display: flex;
    justify-content: center;
    align-items: center;
    white-space: nowrap;
    width: 100%;
    margin-top: 3vh;
    margin-bottom: 3vh;
    }

    .divider::before,
    .divider::after {
    content: "";
    background-color: white;
    height: 2px;
    flex-grow: 1;
    }

    .divider-small::before,
    .divider-small::after {
    height: 1px;
    }

    .divider-medium::before,
    .divider-medium::after {
    height: 4px;
    }

    .divider-large::before,
    .divider-large::after {
    height: 8px;
    }

    .divider-justify-end::after,
    .divider-justify-start::before {
    flex-grow: 0;
    flex-basis: 3%;
    }

    .divider-content {
    padding-inline-start: 10vh;
    padding-inline-end: 10vh;
    color: white;
    }

    .divider-vertical {
    height: auto;
    margin: 0 var(--fluid-16);
    width: var(--fluid-16);
    flex-direction: column;
    align-self: stretch;
    }

    .divider-vertical::before,
    .divider-vertical::after {
    width: 1vh;
    }

    .divider-vertical.divider-small::before,
    .divider-vertical.divider-small::after {
    width: 1px;
    }

    .divider-vertical.divider-medium::before,
    .divider-vertical.divider-medium::after {
    width: 2vh;
    }

    .divider-vertical.divider-large::before,
    .divider-vertical.divider-large::after {
    width: 3vh;
    }

    .divider-vertical .divider-text {
    padding-inline-start: var(--fluid-24);
    padding-inline-end: var(--fluid-24);
    padding-block-start: var(--fluid-6);
    padding-block-end: var(--fluid-6);
    }
</style>

<script>
    export let isVertical = false; // default orientation value
    export let justify = ''; // default position value
    export let size = ''; // default size value
    
    let slots = $$props.$$slots;

    const dividerClasses = [
        "divider",
        isVertical ? "divider-vertical" : "",
        justify ? `divider-${justify}` : "",
        size ? `divider-${size}` : "",
    ]    
    .filter((dividerClass) => dividerClass.length)
    .join(" ");
</script>

<div class={dividerClasses}>
    {#if slots && slots.dividerContent}
        <div class="divider-content">
            <slot name="dividerContent" />
        </div>
    {/if}
</div>