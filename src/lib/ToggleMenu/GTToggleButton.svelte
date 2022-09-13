<script lang="ts"></script>
<style>
    :root {
        --icon-size: 10px;
        --icon-position: 30%;
        --icon-color: black;
        --fill-color: lightseagreen;
    }
    .greater-arrow {
        position: relative;
        padding: 0 18px;
    }
    .greater-arrow:before,
    .greater-arrow:after {
        content: '';
        left: var(--icon-position);
        border: solid transparent;
        height: 0;
        width: 0;
        position: absolute;
    }
    .greater-arrow:after {
        border-left-color: var(--fill-color);
        border-width: var(--icon-size);
        margin-top: calc(var(--icon-size) * -1);
    }
    .greater-arrow:before {
        /* border-color: rgba(194, 225, 245, 0); */
        /* border-left-color: #F39200; */
        border-left-color: var(--icon-color);
        border-width: calc(var(--icon-size) + 5px);
        margin-top: calc((var(--icon-size) + 5px) * -1);
    }
</style>

<div class="greater-arrow"></div>