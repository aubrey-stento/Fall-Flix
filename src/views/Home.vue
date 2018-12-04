<template>
  <div class= "home container-fluid">
    <div class="row">
      <div class="col">
        <h1>Welcome to Vue-Music</h1>
      </div>
    </div>
     <div class="row">
      <div class="col">
        <h4>Searching For: {{query}}</h4>
        <form @submit.prevent="search">
          <input type="text" placeholder="Search" v-model='query'>
          <button type="submit">Search</button>
        </form>
  </div>
  </div>
  <!-- <-- Components Go Here -->
<div class="row justify-content-around mt-5 pb-5">
      <div class="col-5">
        <results></results>
      </div>
      <div class="col-5">
        <preview></preview>
      </div>
    </div>
  </div>
</template>

<script>
import Results from '@/components/Results.vue'
import Preview from '@/components/Preview.vue'
export default {
    name: 'home',
    data() {
      return {
        query: ''
      }
    },
    computed: {
      results() {
        return this.$store.state.searchResults
      }
    },
    methods: {
      search() {
        this.$store.dispatch('search', this.query)
      }
    },
    components: {
      Results,
      Preview
    }
  }
</script>

<style>
  .home {
    background-color: rgb(240, 239, 233)
  }
</style>