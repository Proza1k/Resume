<script>
  import Box from "../../box/box.svelte"
</script>

<Box>
  <div class="tab-panel">
    <slot />
  </div>
</Box>

<style>
  .tab-panel {
    width: 700px;
    min-height: 800px;
    height: auto;
  }
</style>
