<script>
  import { writable } from "svelte/store";

  import Box from "../box/box.svelte";
  import Backend from "./table/backend.svelte";
  import Contact from "./table/contact.svelte";
  import Header from "./menu/header/header.svelte";
  import TabPanel from "./table/tab-panel.svelte";
  import Frontend from "./table/frontend.svelte";
  import Selector from "./menu/body/selector/selector.svelte";

  let spinners = [
    {
      name: "Frontend",
      component: Frontend,
    },
    {
      name: "Backend",
      component: Backend,
    },
    {
      name: "Contact",
      component: Contact
    }
  ];

  const onClick = (spinner) => {
    $selected = selectComponent(spinner, spinners);
    flag.set(false)
  };

  const selectComponent = (selectTitle, spinners) => {
    const selected = spinners.find((spinner) => spinner.name === selectTitle);
    return selected;
  };

  let flag = writable(true)
  let selected = writable([]);
</script>

<Box>
  <div class="menu">
    <Header />
    {#each spinners as spinner}
      <Selector text={spinner.name} onClick={() => onClick(spinner.name)} />
    {/each}
  </div>
</Box>
<TabPanel {spinners}>
  <div class="header">
    {#if $flag === true}
      <h2>HI! MY NAME IS YAROSLAV</h2>
    {:else}
      <h2>{$selected.name}</h2>
    {/if}
  </div>
  <Box>
    <svelte:component this={$selected.component} />
  </Box>
</TabPanel>

<style>
  .header {
    border-bottom: 1px solid #919191;
  }

  .menu {
    width: 300px;
    display: flex;
    align-items: center;
    flex-direction: column;
  }
</style>
