<template>
  <div>
    <Navbar-menu />
    <div class="container">
      <div class="row mt-4">
        <div class="col">
          <h2>
            Daftar
            <strong>Mobil</strong>
          </h2>
        </div>
      </div>

      <div class="row mt-3">
        <div class="col">
          <div class="input-group mb-3">
            <input
              v-model="search"
              type="text"
              class="form-control"
              placeholder="Cari Mobil"
              aria-label="Cari Mobil"
              aria-describedby="basic-addon1"
              @keyup="searchCar"
            />
            <span class="input-group-text" id="basic-addon1"><b-icon-search></b-icon-search></span>
          </div>
        </div>
      </div>

      <div class="row mb-4">
        <div class="col-md-4 mt-5" v-for="product in products" :key="product.id">
          <CarsCard :product="product" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import NavbarMenu from "@/components/NavbarMenu.vue";
import CarsCard from "@/components/CarsCard.vue";
import axios from "axios";

export default {
  name: "CarsView",
  components: {
    NavbarMenu,
    CarsCard
  },
  data() {
    return {
      products: [],
      search:'',
    };
  },
  methods: {
    setProducts(data) {
      this.products = data;
    },
    searchCar(){
      axios
      .get("http://localhost:3000/Cars?q="+this.search)
      .then(response => this.setProducts(response.data))
      .catch(error => console.log(error)); 
    }
  },
  mounted() {
    axios
      .get("http://localhost:3000/Cars")
      .then(response => this.setProducts(response.data))
      .catch(error => console.log(error));
  }
};
</script>

<style>
</style>