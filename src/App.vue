<template>
  <Header />
  <DataTitle />
  <CountrySelect />
  <DataBoxes />
  <div>
    <router-view />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import CountrySelect from './components/CountrySelect.vue';
import DataBoxes from './components/DataBoxes.vue';

export default {
  components: {
    Header,
  },

}
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}

body {
  background: url('https://images.unsplash.com/photo-1667513149021-ebbde2c416bd?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1770&q=80') no-repeat center center fixed;
  background-size: cover;
}
</style>
