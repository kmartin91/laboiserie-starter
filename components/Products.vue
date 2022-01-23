<template>
  <section class="products">
    <div class="cards_wrapper">
      <h2 class="product_title">Products</h2>
      <div class="cards">
        <a class="arrow" href="#">
          <svg width="8" height="12" viewBox="0 0 8 12" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M7.21015 10.4594C7.59661 10.8128 7.59661 11.3841 7.21015 11.7349C6.82369 12.0871 6.19929 12.0897 5.81282 11.7349L0.289847 6.63794C-0.0966174 6.28579 -0.0966173 5.71584 0.289847 5.36108L5.81282 0.264109C6.19785 -0.0880364 6.82369 -0.0880364 7.21015 0.264109C7.59662 0.617558 7.59662 1.18882 7.21015 1.53966L2.68073 6.00147L7.21015 10.4594Z" fill="currentColor"></path>
          </svg>
        </a>

        <div v-if="clothes.pageProps" v-for="c in clothes.pageProps.products.slice(0, 7)" class="card">
          <div class="card_content_wrapper">
            <div class="card_content">
              <a class="card_content_link_img" href="#">
                <img class="card_content_img" :src="c.node.thumbnail.url" alt="">
              </a>
              <a href="#" class="card_title">
                {{ c.node.name }}
              </a>
              <p class="card_price">
                <span style="text-decoration:line-through;" v-if="c.node.variants[0].pricing.priceUndiscounted.gross.amount !== c.node.variants[0].pricing.price.gross.amount">{{ c.node.variants[0].pricing.priceUndiscounted.gross.amount }}</span>
                <span>{{ c.node.variants[0].pricing.price.gross.amount }}</span>
                <span class="text-xs">€</span>
              </p>
            </div>
          </div>
        </div>
        <a class="arrow" href="#">
          <svg width="8" height="12" viewBox="0 0 8 12" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M0.289849 1.54064C-0.0966146 1.18719 -0.0966145 0.615928 0.28985 0.265087C0.676314 -0.087058 1.30071 -0.0896664 1.68718 0.265087L7.21015 5.36206C7.59662 5.71421 7.59662 6.28416 7.21015 6.63892L1.68718 11.7359C1.30215 12.088 0.676312 12.088 0.289848 11.7359C-0.0966159 11.3824 -0.0966159 10.8112 0.289848 10.4603L4.81927 5.99853L0.289849 1.54064Z" fill="currentColor"></path>
          </svg>
        </a>
      </div>
    </div>
  </section>
</template>

<style>
.products {
  background-color: #dbdedb;
  padding: 3rem;
}

.product_title {
  text-transform: uppercase;
  font-size: 32px;
  font-weight: bold;
}

.arrow {
  color: inherit;
  text-decoration: inherit;
  padding-right: 1.5rem;
  display: block;
}

.cards_wrapper {
  width: 100%;
  margin-left: auto;
  margin-right: auto;
  padding-left: 1rem;
  padding-right: 1rem;
}

.cards {
  display: flex;
  align-items: center;
  margin-top: 1rem;
}
.card {
  margin-bottom: 1.5rem;
  width: 350px;
  padding-left: .75rem;
  padding-right: .75rem;
}

.card_content_wrapper {
  margin-bottom: 1.5rem;
  width: 100%;
  padding-left: .75rem;
  padding-right: .75rem;
}

.card_content {
  height: 100%;
  border-radius: .875rem;
  --tw-bg-opacity: 1;
  background-color: rgba(255,255,255,var(--tw-bg-opacity));
  padding: 1.5rem 2.5rem;
}

.card_content_link_img {
  color: inherit;
  text-decoration: inherit;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 2rem;
  display: block;
  max-width: max-content;
}

.card_content_img {
  border-style: solid;
  display: block;
  vertical-align: middle;
  max-width: 100%;
  height: 10rem;
  object-fit: cover;
}

.card_title {
  margin: 0 0 1rem;
  font-family: Poppins,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,"Noto Sans",sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol","Noto Color Emoji";
  font-size: 1.25rem;
  font-weight: 500;
  line-height: 1.5rem;
  color: inherit;
  text-decoration: inherit;
}

.card_price {
  margin-top: 0.6rem;
  color: rgba(31, 35, 47, 0.5);
}
</style>

<script>
export default {
  name: "Products",
  data() {
    return {
      clothes: [],
    };
  },
  async fetch() {
    this.clothes = await fetch(
      "https://la-boiserie.fr/_next/data/Rw8sEjLiaAlmAipHCg0Oc/vetements.json"
    ).then((res) => res.json());
  },
  mounted() {
    console.log(this.clothes);
  },
};
</script>
