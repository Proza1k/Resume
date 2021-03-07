<script>
  import { writable } from "svelte/store"

  export let source
  export let alt

  const open = writable(false)

  const onClick = () => {
    open.set(!$open)
  }
</script>

<div class="content">
  <img class="image" src={source} {alt} on:click={onClick} />
  <div class="box">
    <div class="accordion" class:open={$open}>
      {#if open}
        <slot />
      {/if}
    </div>
  </div>
</div>

<style>
  .accordion {
    display: none;
  }

  .content {
    display: flex;
  }

  .image {
    width: 100px;
    height: 100px;
    border-radius: 50% 50% 0% 0%;
    margin: 20px;
  }

  .open {
    display: block;
  }

  .box {
    background: #fff;
    padding: 10px;
    min-width: 150px;
    max-width: 1200px;
    height: auto;
    width: auto;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 10px;
    margin: 20px;
  }
</style>
