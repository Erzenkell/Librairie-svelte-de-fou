<script lang="ts">
    type ImageType = {
        title: string
        src: string
    }
    export let images: ImageType[]
</script>

<ul id='default-carousel' class="flex scrollbar-hide overflow-x-auto gap-6 snap-x snap-mandatory before:shrink-0 before:w-[30vw] after:shrink-0 after:w-[30vw]" data-carousel="static">
    
    {#each images as {title,src} }
    <li class="self-center shrink-0 snap-center" data-carousel-item>
        <img class="" {title} {src} alt={title} />
    </li>     
    {/each}

</ul>

