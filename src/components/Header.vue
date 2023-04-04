<template>
  <header class="container">

    <div class="text">

      <i class="fa-solid fa-virus-covid"></i>
      Covid-19 LASKURI
    </div>

    <p>
      API
      <a class="link-api" href="https://covid19api.com">
        covid19api</a>
    </p>
  </header>
</template>

<script>
export default {
  name: 'Header',

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  width: 100%;
  text-align: center;
  padding: 10px 20px 50px 20px;
  background-color: #2065aab3;
}

.text {
  font-size: 50px;
  font-weight: bold;
  color: #fff;
}
</style>
