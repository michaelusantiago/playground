<script lang="ts">
    import Fa from "svelte-fa";
    import { faFlag, faRefresh } from "@fortawesome/free-solid-svg-icons";
    export let value: string;
    export let show: boolean;

    const onClickCrud = async (e: Event) => {
        let button = (e.target) as HTMLButtonElement
        if (!button.id) {
            button = button.parentElement as HTMLButtonElement
            if (button.id === 'crud-refresh' || button.nodeName === 'g') {
                if (value === 'crud') {
                    console.log('crud refresh')
                    return
                }
            }
        }
        value = 'crud'
    }
</script>

<style lang="postcss">
    :root {
        --sb-fixed-width: 400px;
        --show-crud-refresh: hidden;
    }

    .active {
        @apply bg-gray-600 transition duration-150 ease-in-out;
    }

    .active > #crud-refresh {
        --show-crud-refresh: visble;
    }

    .side-bar {
        --sb-width: 0; 
        /* left: -400px; */
        width: var(--sb-width);
        overflow-x: hidden;
        position: relative;
        /* transition: width 0.2s, left 0.8s; */
        transition: width 0.2s;
    }

    .show-side-bar {
        --sb-width: var(--sb-fixed-width);
        /* left: 0; */
        /* transition: width 0.2s, left 0.2s; */
    }

    .navi-butt {
        display: flex;
        align-items: center;
        color: aliceblue;
        flex-shrink: 0;
        box-sizing: border-box;
        padding: 5px;
        cursor: pointer;
    }
    .navi-butt button:first-child {
        display: flex;
        align-items: center;
        flex: 1;
        padding: 10px;
        min-width: 10em;
    }
    #crud-refresh {
        visibility: var(--show-crud-refresh);
        padding: 15px;
    }
    #crud-refresh:hover { color: lightskyblue; }
</style>

<div class:show-side-bar={show} class="side-bar bg-gray-700 overflow-auto">
    <ul>
        <li>
            <div class:active="{value === 'crud'}" class="navi-butt" on:click={onClickCrud}>
                <button><Fa class="mr-2" icon={faFlag} />CRUD WEALTHY</button>
                <button id='crud-refresh'><Fa icon={faRefresh} /></button>
            </div>
        </li>
        <li>
            <div class:active="{value === 'toggle_menu'}" class="navi-butt">
                <button on:click={() => value = "toggle_menu"}>
                    <Fa class="mr-2" icon={faFlag} />
                    ToggleMenu
                </button>
            </div>
        </li>
        <li>
            <div class:active="{value === 'cards'}" class="navi-butt">
                <button on:click={() => value = "cards"} class="w-full">
                    <Fa class="mr-2" icon={faFlag} />
                    Cards
                </button>
            </div>
        </li>
        <li>
            <div class:active="{value === 'modalwindow'}" class="navi-butt">
                <button on:click={() => value = "modalwindow"} class="w-full">
                    <Fa class="mr-2" icon={faFlag} />
                    Modal Window 
                </button>
            </div>
        </li>
        <li>
            <div class:active="{value === 'slide'}" class="navi-butt">
                <button on:click={() => value = 'slide'} class="w-full">
                    <Fa class="mr-2" icon={faFlag} />
                    Slide
                </button>
            </div>
        </li>
        <li>
            <div class:active="{value === 'tabs'}" class="navi-butt">
                <button on:click={() => value = "tabs"} class="w-full">
                    <Fa class="mr-2" icon={faFlag} />
                    Tabs
                </button>
            </div>
        </li>
        <li>
            <div class:active="{value === 'notification'}" class="navi-butt">
                <button on:click={() => value = "notification"} class="w-full">
                    <Fa class="mr-2" icon={faFlag} />
                    Notification
                </button>
            </div>
        </li>
        <li>
            <div class:active="{value === 'radio_button'}" class="navi-butt">
                <button on:click={() => value = "radio_button"} class="w-full">
                    <Fa class="mr-2" icon={faFlag} />
                    Radio Button
                </button>
            </div>
        </li>
        <li>
            <div class:active="{value === 'container'}" class="navi-butt">
                <button on:click={() => value = "container"} class="w-full">
                    <Fa class="mr-2" icon={faFlag} />
                    Container
                </button>
            </div>
        </li>
        <li>
            <div class:active="{value === 'playground'}" class="navi-butt">
                <button on:click={() => value = "playground"} class="w-full">
                    <Fa class="mr-2" icon={faFlag} />
                    Playground
                </button>
            </div>
        </li>
        <li>
            <div class:active="{value === 'help'}" class="navi-butt">
                <button on:click={() => value = "help"} class="w-full">
                    <Fa class="mr-2" icon={faFlag} />
                    Help
                </button>
            </div>
        </li>
    </ul>
</div>
