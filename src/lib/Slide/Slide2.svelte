<script lang="ts">
    import { onMount } from "svelte";

    let index = 1;
    let direction = -1;
    
    const images = [
        { id: 1, src: new URL('../../assets/ws images/a.jpg', import.meta.url).href, class: '' },
        { id: 2, src: new URL('../../assets/ws images/b.jpg', import.meta.url).href, class: '' },
        { id: 3, src: new URL('../../assets/ws images/c.jpg', import.meta.url).href, class: '' },
        { id: 4, src: new URL('../../assets/ws images/d.jpg', import.meta.url).href, class: '' },
        { id: 5, src: new URL('../../assets/ws images/e.jpg', import.meta.url).href, class: '' },
        { id: 6, src: new URL('../../assets/ws images/f.jpg', import.meta.url).href, class: '' },
        { id: 7, src: new URL('../../assets/ws images/g.jpg', import.meta.url).href, class: '' }
    ]

    const onLeftButton = (e: Event)  => {
        if ((images.length === 0) || (images.length <= 1)) return

        direction = -1
        if (index !== 2) index--

        const img_to_down = document.getElementById(`img${index}`)
        img_to_down.classList.remove("scale-up")
        img_to_down.classList.remove("move")
        img_to_down.classList.add("scale-down")
        
        const img_to_up = document.getElementById(`img${index-1}`)
        if (img_to_up) img_to_up.classList.add("scale-up")
    }

    const onRightButton = (e: Event)  => {
        if (images.length === 0) return

        direction = -1
        if (index === images.length + 1) return

        const img_to_up = document.getElementById(`img${index}`)
        img_to_up.classList.add("scale-up")
        
        const img_to_down = document.getElementById(`img${index-1}`)
        if (img_to_down) {
            if (img_to_down.classList.contains("scale-up")) {
                img_to_down.classList.remove("scale-up")
                img_to_down.classList.add("scale-down")
            }
        }

        images.forEach((_, i) => {
            const img = document.getElementById(`img${i + 1}`)
            img.classList.add("move")
        })

        index++
    }

    onMount(async () => onRightButton(null))
</script>

<style>
    .images-container {
        position: relative;
        display: flex;
        justify-content: left;
        align-items: center;
        background-color: white;
        height: 15em;
        width: 29em;
        overflow: hidden;
    }

    .images-container img {
        position: relative;
        width: 9.7em;
        opacity: 0.4;
    }

    .button-left {
        border-top-left-radius: 50px;
        border-bottom-left-radius: 50px;
    }

    .button-right {
        border-top-right-radius: 50px;
        border-bottom-right-radius: 50px;
    }

    .move {
        transition: .3s ease-in;
        transform: translateX(calc(var(--left-x) * var(--direction)));
    }

    .scale-down {
        transition: .3s ease-in;
        scale: unset;
        transform: translateX(calc(var(--left-x) * var(--direction)));
        opacity: 0.4;
    }

    .scale-up {
        transition: .3s ease-in;
        transform: translateX(calc(var(--left-x) * var(--direction))) scale(1.5);
        opacity: 1 !important;
        z-index: 1;
    }
</style>

<div class="flex justify-center items-center" style="--left-x: {9.7 * (index - 1)}em; --direction: {direction};">
    <button on:click={onLeftButton} class="button-left bg-slate-300 px-7 py-2 w-[40px]">&lt;</button>
    <div class="images-container">
        {#each images as image, index (image.id)}
            <img
                style:left="{2 * 9.7}em"
                id={`img${index+1}`} src={image.src}
                class={`${index}`}
                alt=""
            />
        {/each}
    </div>
    <button on:click={onRightButton} class="button-right bg-slate-300 w-[40px] px-7 py-2">&gt;</button>
</div>