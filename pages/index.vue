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

<style>
@import url('https://fonts.googleapis.com/css?family=Montserrat:300,400,700');

body{
  margin:0;
  padding:0;
}
h1{
  font-family: 'Montserrat', sans-serif;
  font-size:45px;
  font-weight:700;
  text-align:center;
  color:#2c3e50;
}
h2{
  font-family: 'Montserrat', sans-serif;
  font-size:25px;
  font-weight:400;
  text-align:center;
  color:#2c3e50;
}
.row{
  width:100%;
  height:80vh;
  padding:0;
  margin:0;
  display: flex;
  justify-content: center;
  flex-direction: column;
  position:relative;
}

/* -- SVG CSS -- */

.svg-separator{
  display: block;
  background: 0 0;
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9;
  -webkit-transform: translateY(-100%) translateY(2px);
  transform: translateY(-100%) translateY(2px);
  width: 100%;
}
.svg-separator.bottom{
  top: auto;
  bottom: 0;
}
.sep1{
  transform: translateY(-100%) translateY(2px) scale(1,1);
  transform-origin: top;
}
.sep2 {
  transform: translateY(-100%) translateY(2px) scale(1,1);
  transform-origin: top;
}
.sep3 {
  transform: translateY(-100%) translateY(2px) scale(1,1);
  transform-origin: top;
}
.sep4 {
  transform: translateY(-100%) translateY(2px) scale(1,1);
  transform-origin: top;
}
.sep5 {
  transform: translateY(-100%) translateY(2px) scale(1,1);
  transform-origin: top;
}
.sep6 {
  transform: translateY(-100%) translateY(2px) scale(1,1);
  transform-origin: top;
}
.sep7 {
  transform: translateY(-100%) translateY(2px) scale(1,1);
  transform-origin: top;
}
.sep8 {
  transform: translateY(-100%) translateY(2px) scale(1,1);
  transform-origin: top;
}
.sep9 {
  transform: translateY(0%) translateY(-2px) scale(-1,-1);
  transform-origin: bottom;
}
.sep10 {
  transform: translateY(-100%) translateY(2px) scale(1,1);
  transform-origin: top;
}
.sep11 {
  transform: translateY(-100%) translateY(2px) scale(1,1);
  transform-origin: top;
}
.sep12 {
  transform: translateY(-100%) translateY(2px) scale(1,1);
  transform-origin: top;
}

/* -- Row BG Color -- */

.green{background-color:#03a678;}
.green2{background-color:#1bbc9b;}
.red{background-color:#d24d57;}
.light-grey{background-color:#ecf0f1;}
.light-grey2{background-color:#ecf0f1;}
.dark-blue{background-color:#22313f;}
.grey-blue{background-color:#6c7a89;}
.black{background-color:#333;}
.stupid-blue{background-color:#19b5fe;}
</style>
