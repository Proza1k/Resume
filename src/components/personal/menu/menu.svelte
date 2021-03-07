<script>
  import Box from "../../box/box.svelte";
  import Header from "./header/header.svelte";
</script>

<Box>
  <div class="menu">
    <Header />
  </div>
</Box>

<style>
  .menu {
    width: 300px;
    display: flex;
    align-items: center;
    flex-direction: column;
  }
</style>
