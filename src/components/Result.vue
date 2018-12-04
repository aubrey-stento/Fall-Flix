<template>
  <div class="result">
<h4 @click="setActive">{{songData.trackName}}</h4>
  </div>
</template>

<script>
  export default {
    name: 'result',
    props: ['songData'],
    data() {
      return {

      }
    },
    computed: {},
    methods: {
        setActive() {
            this.setActiveCB(this.songData)
            this.$store.dispatch('setActiveSong', this.songData)
        }
    }
  }

</script>

<style>


</style>
