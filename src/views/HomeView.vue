<template>
  <div class="home">
    <NavbarMenu />
    <div class="container">
      <HeroCar />

      <div class="row mt-5">
        <div class="col">
          <h2>
            <strong>Premium</strong> Cars
          </h2>
        </div>
        <div class="col">
          <router-link to="/Cars" class="btn btn-danger float-end">
            <b-icon-eye class="me-2"></b-icon-eye>Lihat Semua
          </router-link>
        </div>
      </div>

      <div class="row mb-4">
        <div class="col-md-4 mt-5" v-for="product in products" :key="product.id">
          <CarsCard :product="product"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import NavbarMenu from "@/components/NavbarMenu.vue";
import HeroCar from "@/components/HeroCar.vue";
import CarsCard from "@/components/CarsCard.vue";
import axios from "axios";

export default {
  name: "HomeView",
  components: {
    NavbarMenu,
    HeroCar,
    CarsCard
  },
  data() {
    return {
      products: []
    };
  },
  methods: {
    setProducts(data) {
      this.products = data;
    }
  },
  mounted() {
    axios
      .get("http://localhost:3000/Premium-Cars")
      .then((response) => this.setProducts(response.data))
      .catch((error) => console.log(error))
  },
};
</script>
