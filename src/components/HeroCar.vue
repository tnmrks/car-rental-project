<template>
  <div class="hero">
    <!--Dekstop-->
    <div class="d-none d-md-block">
      <div class="row mt-5">
        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h2>
                <strong>Amazing,</strong>
                <br />Car Rent
              </h2>
              <p>Ayo segera rental</p>
              <router-link type="button" class="btn btn-danger" to="/cars">
                <b-icon-arrow-right class="me-2"></b-icon-arrow-right>Rental
              </router-link>
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <img src="../assets/images/car1.png" width="100%" />
        </div>
      </div>
    </div>

    <!--Mobile-->
    <div class="d-sm-block d-md-none">
      <div class="row mt-5">
        <div class="col-md-6 mb-3">
          <img src="../assets/images/car1.png" width="100%" />
        </div>
        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h2>
                <strong>Amazing,</strong>
                <br>Car Rent
              </h2>
              <p>Ayo segera rental</p>
              <button type="button" class="btn btn-danger">
                <b-icon-arrow-right class="me-2"></b-icon-arrow-right>Rental
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeroCar"
};
</script>

<style>
</style>