<template>
  <div class="app">
    <div class="header container h-100 p-5">
      <h1 class="mb-5">Weather App</h1>
      <div class="d-flex justify-content-center h-100">
        <div class="search-bar w-50 mx-2">
          <input type="text" class="input form-control" v-model="city" placeholder="Enter your city">
        </div>
        <button class="btn-search btn btn-primary" @click="searchweather">Search</button>
      </div>
    </div>
    <Weather :city="city" v-if="showWeather" />
  </div>
</template>



<script>
import Weather from './components/Weather.vue'

export default {
  name: "App",
  components: {
    Weather,
  },
  data() {
    return {
      city: 'Saran,Bihar,In',
      showWeather: 'false'
    }
  },
  methods: {
    async searchweather() {
      this.showWeather = false;
      await this.$nextTick();
      this.showWeather = true;
    }
  }
};
</script>

<style>
body {
  background-color: #121212 !important;
}

.header {
  background-color: #212730;
  border-radius: 20px;
  color: #fff;
  text-align: center;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  margin-top: 5rem;
}

.btn-search {
  background-image: linear-gradient(to right, cyan, magenta);
}
</style>
