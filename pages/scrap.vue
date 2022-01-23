<template>
  <div>
    <p>Accessoires</p>
    <ul>
      <li v-for="a in accessories.pageProps.products">{{ a.node.name }} {{ a.node.thumbnail.url }}</li>
    </ul>
    <p>Vêtements</p>
    <ul>
      <li v-for="a in clothes.pageProps.products">{{ a.node.name }} {{ a.node.thumbnail.url }}</li>
    </ul>
    <p>Stickers</p>
    <ul>
      <li v-for="a in stickers.pageProps.products">{{ a.node.name }} {{ a.node.thumbnail.url }}</li>
    </ul>
    <p>Montres</p>
    <ul>
      <li v-for="a in watches.pageProps.products">{{ a.node.name }} {{ a.node.thumbnail.url }}</li>
    </ul>
    <p>Draisiennes</p>
    <ul>
      <li v-for="a in wheelchairs.pageProps.products">{{ a.node.name }} {{ a.node.thumbnail.url }}</li>
    </ul>
    <p>Cross</p>
    <ul>
      <li v-for="a in cross.pageProps.products">{{ a.node.name }} {{ a.node.thumbnail.url }}</li>
    </ul>
    <p>Contest</p>
    <ul>
      <li>{{ contest.pageProps.product.name }} {{ contest.pageProps.product.thumbnail.url }}</li>
    </ul>
  </div>

</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      accessories: [],
      clothes:[],
      stickers:[],
      watches:[],
      wheelchairs:[],
      cross:[],
      contest:[],
    }
  },
  async fetch() {
    this.accessories = await fetch(
      'https://la-boiserie.fr/_next/data/Rw8sEjLiaAlmAipHCg0Oc/accessoires.json'
    ).then(res => res.json())

    this.clothes = await fetch(
      'https://la-boiserie.fr/_next/data/Rw8sEjLiaAlmAipHCg0Oc/vetements.json'
    ).then(res => res.json())

    this.stickers = await fetch(
      'https://la-boiserie.fr/_next/data/Rw8sEjLiaAlmAipHCg0Oc/stickers.json'
    ).then(res => res.json())

    this.watches = await fetch(
      'https://la-boiserie.fr/_next/data/Rw8sEjLiaAlmAipHCg0Oc/montres.json'
    ).then(res => res.json())

    this.wheelchairs = await fetch(
      'https://la-boiserie.fr/_next/data/Rw8sEjLiaAlmAipHCg0Oc/draisiennes.json'
    ).then(res => res.json())

    this.cross = await fetch(
      'https://la-boiserie.fr/_next/data/Rw8sEjLiaAlmAipHCg0Oc/cross.json'
    ).then(res => res.json())

    this.contest = await fetch(
      'https://la-boiserie.fr/_next/data/Rw8sEjLiaAlmAipHCg0Oc/contest.json'
    ).then(res => res.json())
  },
  mounted() {
    console.log(this.contest);
  }
}
</script>
