<script>
  import Table from "./table.svelte"

  const getSrcImage = (card) => {
    return './img/contact/' + card.image + '.svg'
  }

  let cards = [
      {
          name: 'Ulyanovsk, Russia',
          image: 'city'
      },
      {
          name: '+7 (927) 631 44 12',
          image: 'phone',
          href: 'tel:+7 916 559-71-10'
      },
      {
          name: 'vdovin_yar@mail.ru',
          image: 'mail',
          href: 'mailto:vdovin_yar@mail.ru'
      },
      {
          name: 'Github',
          image: 'github',
          href: 'https://github.com/proza1k'
      },
      {
          name: 'VK',
          image: 'vk',
          href: 'https://vk.com/vdovin_yar'
      },
  ]
</script>

{#each cards as card}
    <Table src={getSrcImage(card)} name={card.name} href="{card.href}"/>
{/each}