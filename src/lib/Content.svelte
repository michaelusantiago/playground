<script lang="ts">
    // let arr = Array(100).fill("hello world", 0, 100);
    export let id: string;
</script>

<div class="grid grid-rows-[1fr] bg-green-600 w-full">
    <div style:overflow={id === 'slide' ? 'hidden' : 'auto'} class=" bg-green-300">
        <slot name="content">no content</slot>
    </div>
    {#if $$slots.footer}
        <div class="bg-gray-400 footer">
            <slot name="footer"/>
        </div>
    {/if}
</div>