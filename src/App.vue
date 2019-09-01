<template>
  <div id="app">
    <div class="container-fluid">
      <div class="row">
        <div class="col-sm-7">
          <mf-product-view></mf-product-view>
        </div>
        <div class="col-sm-5">
          <mf-product-cart></mf-product-cart>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "app"
  };
</script>

<style>
  #app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
