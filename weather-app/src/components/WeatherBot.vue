<template>
  <div class="form-group container mt-4" style="min-width: 450px;">
    <h1 style="text-align: center;">Weather Bot</h1>
    <div class="d-flex">
      <input v-model="city" id="city" type="text" class="form-control mr-2" placeholder="Add city" />
      <button class="btn btn-primary ml-2" @click.prevent="createWeather">Add city</button>
    </div>

    <table class="table mt-3" v-if="weathers != 0">
      <thead>
        <tr>
          <th scope="col">City</th>
          <th scope="col">MinTemp</th>
          <th scope="col">MaxTemp</th>
          <th scope="col">Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(weather, index) in weathers" :key="weather.city">
          <th class="align-middle" scope="row">{{ weather.city }}</th>
          <td class="align-middle">{{ weather.temp_min }}°C</td>
          <td class="align-middle">{{ weather.temp_max }}°C</td>
          <td><button type="button" class="btn btn-dark" @click="deleteWeather(index)">Delete</button></td>
        </tr>
      </tbody>
    </table>

  </div>
</template>

<script>

export default {
  data() {
    return {
      city: "",
      day: "",
      weathers: []
    }
  },
  methods: {
    createWeather() {
      const temp_min = 1
      const temp_max = 3
      const weather = {
        city: this.city,
        temp_min,
        temp_max
      }
      this.weathers.push(weather)
      this.city = ''

    },
    deleteWeather(index) {
      this.weathers.splice(index, 1)
    }
  },
};
</script>