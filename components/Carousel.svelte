<script>

    import { onMount } from 'svelte'
    
    export let carouselId = "carousel" 

    let carousel;

    function left(){
        carousel.scrollLeft -= carousel.offsetWidth

    }

    function right(){
        carousel.scrollLeft += carousel.offsetWidth
    }

    onMount(() => {
        carousel = document.getElementById(carouselId)
    })

</script>

<div class="w-full h-full relative">
    <div class="w-full top-1/2 flex justify-between px-3 z-10">
        <button class="btn rounded-full self-start" on:click={left}> &lt </button>
        <button class="btn rounded-full self-end" on:click={right}> &gt </button>
    </div>
    <div id={carouselId} class="carousel w-full h-full top-0">
        
        <div id="1" class="carousel-item w-full flex items-center justify-center h-full">
            <div>
                ITEM 1
            </div>
        </div>
        <div id="2" class="carousel-item w-full flex items-center justify-center h-full">
            ITEM 2
        </div>
        <div id="3" class="carousel-item w-full flex items-center justify-center h-full">
            ITEM 3
        </div>
        <div id="4" class="carousel-item w-full flex items-center justify-center h-full">
            ITEM 4
        </div>
    </div>
    
</div>
