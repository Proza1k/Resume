<script>
  import Table from "./table.svelte"

  const getSrcImage = (card) => {
    return '/img/backend/' + card.image + '.png'
  }

  let cards = [
      {
          name: 'SQL',
          image: 'sql'
      },
  ]
</script>

{#each cards as card}
    <Table src={getSrcImage(card)} name={card.name} />
{/each}