
<template>
  <select v-model="selected" class="form-select " @change="onChange()">
    <option value="0">Valitse Maa</option>
    <option v-for="country in countries" :value="country.ID">
      {{ country.Country }}
    </option>
  </select>
</template>

<script>
import { ref } from 'vue';
export default {
  name: 'CountrySelect',
  props: ['countries'],
  setup({ countries }, { emit }) {
    const selected = ref(0);
    return {
      selected,
      onChange() {
        const country = countries.find((item) => item.ID === selected.value);
        emit('get-country', country);
      }
    };
  }
};
</script>


<style scoped>
.form-select {
    margin-top: 10px;
    margin-left: 10px;
    display: block;
    width: 30%;
    border: 1px solid #ccc;
    padding: 1rem 1rem;
    border-radius: 1.25rem;
    cursor: pointer;
}
</style>