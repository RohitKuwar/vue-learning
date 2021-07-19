<template>
  <div>
    <h1>List Rendering</h1>
    <h2>Mapping an Array to Elements with v-for</h2>
    <!-- v-for directive to render a list of items based on an array. -->
    <h3 v-for="framework in frameworks" :key="framework">{{ framework }}</h3>

    <!-- v-for with an array of object -->
    <h3 v-for="fullname in fullnames" :key="fullname">{{ fullname.fname }} {{ fullname.lname }}</h3>

    <!-- v-for with an array of array -->
    <div v-for="actor in actors" :key="actor.name">
    <h3>{{ actor.name }}</h3>
    <h4 v-for="movie in actor.movies" :key="movie">{{ movie }}</h4>
  </div>

  <h2>Iterating the properties of an Objects to Elements with v-for</h2>
  <h3 v-for="player in playerInfo" :key="player.key">{{ player }}</h3>

  <template v-for="framework in frameworks" :key="framework">
    <h3>{{ framework }}</h3>
    <hr>
  </template>

  <h2>Conditional list rendering</h2>
  <template v-for="framework in frameworks" :key="framework">
    <h3 v-if="framework === 'Vue'">{{ framework }}</h3>
  </template>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        frameworks: ['React', 'Angular', 'Vue'],
        stacks: ['frontend', 'backend', 'fullstack'],
        fullnames: [
          { fname: 'Mahedrasingh', lname: 'Dhoni' },
          { fname: 'Suresh', lname: 'Raina' },
          { fname: 'Ravindra', lname: 'Jadeja' }
        ],
        actors: [
        {
          name: 'Christian Bale',
          movies: ['Batman', 'American Psycho'],
        },
        {
          name: 'Di Caprio',
          movies: ['Titanic', 'Inception'],
        },
      ],
      playerInfo: {
        name: 'Sachin Tendulkar',
        role: 'Batsman',
        centuries: 100,
      },
      }
    }
  }
</script>

<style scoped>

</style>