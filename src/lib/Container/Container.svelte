<script lang="ts">
    import Container1 from "./Container1.svelte";
    import Container2 from "./Container2.svelte";
</script>

<style lang="postcss">
    main { margin: 5em; }
</style>

<main>
    <Container1 header_title="No props, used defaults">
        <div class="p-5">
            <div>Ratione animi molestiae suscipit et, tempore sint dolores quisquam nulla in minima provident quis iste! Quaerat commodi tempore inventore, nisi voluptate tempora!</div>
            <br/>
            <button class="bg-gray-500 border float-right border-solid px-7 py-2">Hello</button>
        </div>
    </Container1>

    <br />

    <Container1 header_title="With custom colors, etc (props)"
        hd_border_color="#222"
        hd_bg_color="yellow"
        hd_text_color="blue"
        hd_icon_color="purple">
        <div class="p-5">
            <div>Ratione animi molestiae suscipit et, tempore sint dolores quisquam nulla in minima provident quis iste! Quaerat commodi tempore inventore, nisi voluptate tempora!</div>
            <br/>
            <button class="bg-gray-500 border float-right border-solid px-7 py-2">Hello</button>
        </div>
    </Container1>

    <br />

    <Container2 header_title="No longer dependent on GTToggle component, and yet customizable">
        <div class="p-5">
            <div>Ratione animi molestiae suscipit et, tempore sint dolores quisquam nulla in minima provident quis iste! Quaerat commodi tempore inventore, nisi voluptate tempora!</div>
            <br/>
            <button class="bg-gray-500 border float-right border-solid px-7 py-2">Hello</button>
        </div>
    </Container2>
</main>
