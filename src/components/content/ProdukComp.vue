<template>
  <section id="portfolio" class="portfolio">
    <div class="container" data-aos="fade-up">
      <div class="section-title">
        <h2 class="col-lg-12">Parfume</h2>
      </div>

      <select class="form-select w-25 mx-auto mb-4" @change="onChange($event)" id="filter">
        <option :value="category.value" v-for="(category, i) in categories" :key="i">{{ category.name }}</option>
      </select>

      <div class="row portfolio-container" data-aos="fade-up" data-aos-delay="300">
        <div class="col-lg-4 col-md-6 portfolio-item filter-app" v-for="(product, i) in filterProducts" :key="i">
          <div class="portfolio-wrap">
            <img :src="product.image" class="img-fluid" alt="" />
            <div class="portfolio-info">
              <h4>{{ product.name }}</h4>
              <p>Rp. {{ Intl.NumberFormat().format(product.harga) }}</p>
              <div class="portfolio-links">
                <a :href="product.link"><i class="bx bx-link"></i></a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "ProdukComp",
  data: () => ({
    products: [
      {
        name: "OMNIA AMETHYSTE",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-AMETHYSTE-i.11905962.11004598530?sp_atk=305f884f-53ea-4f81-b0a8-964bab71b4cd&xptdk=305f884f-53ea-4f81-b0a8-964bab71b4cd",
        image: "assetImage/IMG PRODUK/OMNIA AMETHYSE.jpg",
        harga: 89000,
        type: "wanita",
      },
      {
        name: "BLACK OPIUM",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-BLACK-OPI-i.11905962.9050927893?sp_atk=7c8668f0-2bf8-44d9-bfa8-f3bca435b9f3&xptdk=7c8668f0-2bf8-44d9-bfa8-f3bca435b9f3",
        image: "assetImage/IMG PRODUK/BLACK OPIUM.jpg",
        harga: 89000,
        type: "unisex",
      },
      {
        name: "VS SCANDALOUS",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-SCANDALOUS-i.11905962.9466550685?sp_atk=c03cdf8f-eda2-4437-b6bf-039a9bd63a89&xptdk=c03cdf8f-eda2-4437-b6bf-039a9bd63a89",
        image: "assetImage/IMG PRODUK/VS SCANDALOUS.jpg",
        harga: 89000,
        type: "wanita",
      },
      {
        name: "DIOR SAUVAGE",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-SAUVAGE-i.11905962.8474516168?sp_atk=97c125e6-5967-4ccb-b52b-1af0807e6db9&xptdk=97c125e6-5967-4ccb-b52b-1af0807e6db9",
        image: "assetImage/IMG PRODUK/DIOR SAUVAGE FOR MEN.jpg",
        harga: 89000,
        type: "pria",
      },
      {
        name: "VS BOMBSHELL",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-BOMBSHELL-i.11905962.8152978189?sp_atk=d5940f2a-f4dd-4068-ba6c-e47fdc6d139b&xptdk=d5940f2a-f4dd-4068-ba6c-e47fdc6d139b",
        image: "assetImage/IMG PRODUK/VS BOMBSHELL.jpg",
        harga: 89000,
        type: "wanita",
      },
      {
        name: "CH - GOOD GIRL",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-GOOD-GIRL-i.11905962.14672088311?sp_atk=27bfa1fa-203b-4ecb-8b23-4b26f810d247&xptdk=27bfa1fa-203b-4ecb-8b23-4b26f810d247l",
        image: "assetImage/IMG PRODUK/CH - GOOD GIRL.jpg",
        harga: 89000,
        type: "wanita",
      },
      {
        name: "CHNL COCO MADEMOISELLE",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-COCO-MADEMOISELLE-i.11905962.7596832028?sp_atk=10d7c4a6-10be-4233-b38c-8930505cac3b&xptdk=10d7c4a6-10be-4233-b38c-8930505cac3b",
        image: "assetImage/IMG PRODUK/CHNL COCO MADEMOISELLE.jpg",
        harga: 89000,
        type: "wanita",
      },
      {
        name: "LA VIE EST BELLE",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-LA-VIE-EST-B-i.11905962.12966174437?sp_atk=3017805d-894c-4d0a-9a8e-c284ac99dacf&xptdk=3017805d-894c-4d0a-9a8e-c284ac99dacf",
        image: "assetImage/IMG PRODUK/LA VIE EST BELLE.jpg",
        harga: 89000,
        type: "wanita",
      },
      {
        name: "OMNIA CRYSTALLINE",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-CRYSTALLINE-i.11905962.7191705650?sp_atk=8f049343-728e-421d-be1c-55c70e2e87c9&xptdk=8f049343-728e-421d-be1c-55c70e2e87c9",
        image: "assetImage/IMG PRODUK/OMNIA CRYSTALLINE.jpg",
        harga: 89000,
        type: "wanita",
      },
      {
        name: "BACCARAT 540",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-BKRT-i.11905962.21671779193?sp_atk=0f8f756c-89ae-4767-8b79-2424a32fcb60&xptdk=0f8f756c-89ae-4767-8b79-2424a32fcb60",
        image: "assetImage/IMG PRODUK/BACCARAT 540.jpg",
        harga: 89000,
        type: "unisex",
      },
      {
        name: "YSL LIBRE",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-LIBRE-i.11905962.17253522971?sp_atk=e019b2e8-06d0-4266-a221-c2beae53f87a&xptdk=e019b2e8-06d0-4266-a221-c2beae53f87a",
        image: "assetImage/IMG PRODUK/YSL LIBRE.jpg",
        harga: 89000,
        type: "unisex",
      },
      {
        name: "VERSACE EROS",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-EROS-i.11905962.13374975943?sp_atk=e3ef127d-df58-4e85-ac1f-25981d0adec8&xptdk=e3ef127d-df58-4e85-ac1f-25981d0adec8",
        image: "assetImage/IMG PRODUK/VERSACE EROS FOR MEN.jpg",
        harga: 89000,
        type: "pria",
      },
      {
        name: "GC. GUILTY",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-GC-GUILTY-i.11905962.17877592708?sp_atk=9187d689-84f9-4296-849c-b23a1b8ab25c&xptdk=9187d689-84f9-4296-849c-b23a1b8ab25c",
        image: "assetImage/IMG PRODUK/GC. GUILTY.jpg",
        harga: 89000,
        type: "unisex",
      },
      {
        name: "SELENA GOMEZ",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-SLNA-GMZ-i.11905962.18945010481?sp_atk=c5924bdd-e9db-4579-82bb-6695d1f809d7&xptdk=c5924bdd-e9db-4579-82bb-6695d1f809d7",
        image: "assetImage/IMG PRODUK/SELENA GOMEZ.jpg",
        harga: 89000,
        type: "wanita",
      },
      {
        name: "TWILLY D'HERMES",
        link: "https://shopee.co.id/SEMERBAK-Inspired-by-TWILLY-i.11905962.8366547065?sp_atk=9cba1378-3e0f-43ba-8c41-6ad869d0ebed&xptdk=9cba1378-3e0f-43ba-8c41-6ad869d0ebed",
        image: "assetImage/IMG PRODUK/TWILLY D'HERMES.jpg",
        harga: 89000,
        type: "wanita",
      },
    ],
    categories: [
      {
        name: "Semua",
        value: "semua",
      },
      {
        name: "Unisex",
        value: "unisex",
      },
      {
        name: "Pria",
        value: "pria",
      },
      {
        name: "Wanita",
        value: "wanita",
      },
    ],
    filterProducts: [],
  }),
  methods: {
    onChange(event) {
      let valFilter = event.target.value;

      if (valFilter == "semua") {
        this.filterProducts = [...this.products];
      } else {
        this.filterProducts = [
          ...this.products.filter(function (el) {
            return el.type == valFilter;
          }),
        ];
      }
    },
  },
  mounted() {
    this.filterProducts = [...this.products];
  },
};
</script>

<style></style>
