<script>
  import Table from "./table.svelte"

  const getSrcImage = (card) => {
    return '/img/frontend/' + card.image + '.png'
  }

  let cards = [
      {
          name: 'HTML',
          image: 'html'
      },
      {
          name: 'CSS',
          image: 'css'
      },
      {
          name: 'SASS',
          image: 'sass'
      },
      {
          name: 'React',
          image: 'react'
      },
      {
          name: 'Svelte',
          image: 'svelte'
      },
  ]
</script>

{#each cards as card}
    <Table src={getSrcImage(card)} name={card.name} />
{/each}