<script lang="ts">
  import Header from './lib/Header.svelte'
  import SideNav from './lib/SideNav.svelte'
  import Content from './lib/Content.svelte'

  import Employee from './lib/Employee/Employee.svelte'
  import ToggleMenu from './lib/ToggleMenu/ToggleMenu.svelte'
  import Playground from './lib/Playground.svelte'
  import Cards from './lib/Cards/Cards.svelte'
  import ModalWindow from './lib/ModalWindow/ModalWindow.svelte'
  import Slide from './lib/Slide/Slide.svelte'
  import Tabs from './lib/Tabs/Tabs.svelte'
  import Notification from './lib/Notification/Notification.svelte'
  import RadioButton from './lib/RadioButton/RadioButton.svelte'
  import Container from './lib/Container/Container.svelte'

  let menu_selected = "crud"
  let show_menu = true;

  const menu = [
    {id: "crud", content: Employee, footer: null },
    {id: "toggle_menu", content: ToggleMenu, footer: null },
    {id: "cards", content: Cards, footer: null },
    {id: "modalwindow", content: ModalWindow, footer: null },
    {id: "slide", content: Slide, footer: null },
    {id: "tabs", content: Tabs, footer: null },
    {id: "notification", content: Notification, footer: null },
    {id: "radio_button", content: RadioButton, footer: null },
    {id: "container", content: Container, footer: null },
    {id: "playground", content: Playground, footer: null },
  ]

  let current_component = menu.find(menu => menu.id === menu_selected)

  $: {
    const found = menu.find(menu => menu.id === menu_selected);
    if (found)
      current_component = menu.find(menu => menu.id === menu_selected)
    else current_component = null
  }
</script>

<main class="grid grid-rows-[auto_1fr] h-[100vh] bg-blue-300">
  <!-- Header -->
  <Header bind:value={show_menu}/>

  <!-- Content -->
  <div class="flex h-full overflow-auto">
    <SideNav show={show_menu} bind:value={menu_selected} />
    {#if current_component}
      <Content id={current_component.id}>
        <div slot="content"><svelte:component this={current_component.content} /></div>
          <!-- Master Footer (not used)-->
          <div slot="footer">
            {#if current_component.footer}
              <svelte:component this={current_component.footer} />
            {/if}
          </div>
      </Content>
    {:else} <Content id=null /> {/if}
  </div>
</main>

<style lang="postcss">
</style>