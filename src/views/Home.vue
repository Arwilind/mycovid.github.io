<template>
  <main v-if="!loading">

    <CountrySelect :countries="countries" @get-country="getCountryData" />


    <DataTitle :text="title" :dataDate="dataDate" />


    <DataBoxes :stats="stats" />



  </main>


  <main class="error" v-else>
    <div class="fetching-text">

    </div>
    <!-- <img src="loadImage" class="load-image" alt="" /> -->
  </main>
</template>

<script>
import CountrySelect from '@/components/CountrySelect'
import DataTitle from '@/components/DataTitle'
import DataBoxes from '@/components/DataBoxes'

export default {
  name: 'Home',
  components: {
    DataTitle,
    DataBoxes,
    CountrySelect,

  },
  data() {
    return {
      loading: true,
      title: 'Global',
      dataDate: '',
      stats: {},
      countries: [],




    }
  },
  methods: {
    async fetchCovidData() {
      const res = await fetch('https://api.covid19api.com/summary')
      const data = await res.json()
      return data
    },
    getCountryData(country) {
      this.stats = country
      this.title = country.Country

    },
    clearCountryData() {
      this.stats = this.global
      this.title = 'Global'
    }
  },

  async created() {
    const data = await this.fetchCovidData()
    this.dataDate = data.Date
    this.stats = data.Global
    this.countries = data.Countries
    this.loading = false
  },



}
</script>
<style scope>
.load-image {
  width: 100px;
  height: 100px;
  margin: 0 auto;
  display: block;
}

button {
  margin-top: 10px;
  margin-left: 10px;
  background-color: red;

}
</style>