<script>
  export let text
  export let onClick
</script>

<span class="selector" on:click={onClick}>
  {text}
</span>

<style>
  .selector {
    border-top: 1px solid #919191;
    height: 70px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    font-weight: 500;
  }

  .selector:hover {
    background: #585858;
    color: #fff;
    transition: 0.5s;
    opacity: 0.7;
  }
</style>
