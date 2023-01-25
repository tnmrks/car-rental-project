<template>
  <div class="card shadow card-product" style="width: 22rem;">
    <img :src="'./assets/images/' + product.gambar" class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title">{{product.nama}}</h5>
      <p
        class="card-text"
      >Harga Sewa : {{ product.harga_sewa }}</p>
      <a href="#" class="btn btn-danger"><b-icon-key-fill class="me-2"></b-icon-key-fill>Rental</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "CarsCard",
  props: ["product"]
};
</script>

<style>
</style>