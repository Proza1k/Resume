<script>
  export let src
  export let name
  export let href
</script>

<div class="card">
  <img {src} alt={name} class="card-image" />
  <a {href} target="_blank">{name}</a>
</div>

<style>
  .card {
    height: 60px;
    display: flex;
    align-items: center;
    margin: 10px 0;
  }

  .card:hover .card-image {
    transform: rotate(360deg);
    transition: 1s transform ease-in-out;
  }

  a {
    font-size: 20px;
    margin-left: 10px;
    text-decoration: none;
  }

  .card-image {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    transition: 1s transform ease-in-out;
    transform: rotate(0deg);
  }
</style>
