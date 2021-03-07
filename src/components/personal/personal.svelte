<script>
  import { writable } from "svelte/store";

  import Box from "../box/box.svelte";
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
    },
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
  {#if $flag === true}
    <h4>HI! MY NAME IS YAROSLAV</h4>
  {:else}
   <h4>{$selected.name}</h4>
  {/if}
  <svelte:component this={$selected.component} />
</TabPanel>

<style>
  .menu {
    width: 300px;
    display: flex;
    align-items: center;
    flex-direction: column;
  }
</style>
