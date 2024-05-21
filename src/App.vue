<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-primary text-white" height-hint="98">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://tse2.mm.bing.net/th?id=OIP.4vNyzgL9up73zbjJa3v_lAHaC9&pid=Api&P=0&h=180">
          </q-avatar>
          SheeshShoes
        </q-toolbar-title>
      </q-toolbar>
      <q-tabs align="left">
        <q-route-tab to="/Home" label="Home" />
        <q-route-tab to="/Shop" label="Shop" />
        <q-route-tab to="/About" label="About" />
      </q-tabs>
    </q-header>

    <q-page-container>
      <router-view />
      <div class="q-pa-md">
        <q-carousel 
          v-model="slide" 
          animated 
          infinite 
          swipeable 
          height="300px"
          class="my-carousel"
        >
          <q-carousel-slide v-for="(product, index) in products" :key="index" :img-src="product.image" :img-alt="product.name"></q-carousel-slide>
        </q-carousel>

        <q-card class="q-ma-md">
          <q-card-section>
            <div class="text-h6">Featured Products</div>
          </q-card-section>

          <q-card-section>
            <q-list bordered separator>
              <q-item v-for="(product, index) in products" :key="index">
                <q-item-section avatar>
                  <q-avatar>
                    <img :src="product.image" :alt="product.name">
                  </q-avatar>
                </q-item-section>
                <q-item-section>
                  <q-item-label>{{ product.name }}</q-item-label>
                  <q-item-label caption>{{ product.price }}</q-item-label>
                </q-item-section>
              </q-item>
            </q-list>
          </q-card-section>

          <q-card-actions align="right">
            <q-btn flat label="View All" @click="viewAllProducts" />
            <q-btn flat label="Contact" @click="viewAllProducts" />
          </q-card-actions>
        </q-card>
      </div>
    </q-page-container>

    <q-footer elevated class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://tse2.mm.bing.net/th?id=OIP.4vNyzgL9up73zbjJa3v_lAHaC9&pid=Api&P=0&h=180">
          </q-avatar>
          <div>SheeshShoes</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
export default {
  name: 'MainLayout',
  data() {
    return {
      slide: 0,
      products: [
        { name: 'Adidas', image: 'https://tse4.mm.bing.net/th?id=OIP.nygu3F6OprlJ8N9Yc9r72gHaHa&pid=Api&P=0&h=180', price: '$19.99' },
        { name: 'Air Jordan', image: 'https://tse1.mm.bing.net/th?id=OIP.f7bs2l4T3HrpaM2hGtpnggHaHa&pid=Api&P=0&h=180', price: '$21.99' },
        { name: 'Converse', image: 'https://tse3.mm.bing.net/th?id=OIP.k-1aD12PJI0XKPH5Ug0shgHaHa&pid=Api&P=0&h=180', price: '$14.99' },
        { name: 'Vans', image: 'https://tse2.mm.bing.net/th?id=OIP.zqK8RZpbryMnKW1sEd1EoAHaHa&pid=Api&P=0&h=180', price: '$14.99' },
        { name: 'Sepatu Futsal', image: 'https://tse4.mm.bing.net/th?id=OIP.9k1ck11gUCbDrKlU0u8B3AHaHa&pid=Api&P=0&h=180', price: '$10.99' }
      ]
    }
  },
  methods: {
    viewAllProducts() {
      // Action to view all products
    }
  }
}
</script>

<style>
.my-carousel {
  max-width: 500px;
  margin: auto;
}
</style>
