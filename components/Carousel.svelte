<script>

    import { onMount } from 'svelte'
    
    export let carouselId = "carousel" 

    let carousel;

    function left(){
        if(carousel.scrollLeft == 0){
            carousel.scrollLeft += carousel.scrollWidth
        }
        else{
            carousel.scrollLeft -= carousel.offsetWidth
        }
    }

    function right(){
        
        if(carousel.scrollLeft >= carousel.scrollWidth - carousel.offsetWidth - 1){
            
            carousel.scrollLeft = 0
        }else{
            carousel.scrollLeft += carousel.offsetWidth
        }
    }

    onMount(() => {
        carousel = document.getElementById(carouselId)
    })

</script>

<div class="w-full h-full relative">
    <div class="w-full absolute top-1/2 flex justify-between px-3 z-10">
        <button class="btn rounded-full self-start" on:click={left}> &lt </button>
        <button class="btn rounded-full self-end" on:click={right}> &gt </button>
    </div>
    <div id={carouselId} class="carousel w-full h-full absolute top-0">
        
        <div id="1" class="carousel-item w-full flex items-center justify-center h-full">
            ITEM A
        </div>
        <div id="2" class="carousel-item w-full flex items-center justify-center h-full">
            ITEM B
        </div>
        <div id="3" class="carousel-item w-full flex items-center justify-center h-full">
            ITEM C
        </div>
        <div id="4" class="carousel-item w-full flex items-center justify-center h-full">
            ITEM D
        </div>
        <div id="4" class="carousel-item w-full flex items-center justify-center h-full">
            ITEM E
        </div>
    </div>
    
</div>