<script lang="ts">
    const img1 = new URL('../../assets/ws images/a.jpg', import.meta.url).href
    const img2 = new URL('../../assets/ws images/b.jpg', import.meta.url).href
    const img3 = new URL('../../assets/ws images/c.jpg', import.meta.url).href

    let current_index = 0
    let images = [img1, img2, img3, img1, img2, img3]

    const onClickLeftPic = (e: Event) => { if (current_index !== 0) current_index -= 1 }
    const onClickRightPic = (e: Event) => { if (current_index !== images.length - 3) current_index += 1 }
</script>

<style>
    .scroll-space-container {
        display: flex;
        justify-content: space-around;
        align-items: center;
        background-color: white;
        height: 15em;
        width: 35em;
        overflow: hidden;
    }

    .scroll-space-container img {
        width: 10em;
        transition: all ease-in-out;
    }

    .scroll-space-container img:first-child,

    .scroll-space-container img:last-child {
        opacity: 0.3;
        width: 7em;
        cursor: pointer;
    }
</style>

<div class="flex justify-center items-center">
    <div class="scroll-space-container">
        <img on:click={onClickLeftPic} src={images[current_index]} alt=""/>
        <img src={images[current_index + 1]} alt=""/>
        <img on:click={onClickRightPic} src={images[current_index + 2]} alt=""/>
    </div>
</div>