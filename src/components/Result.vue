<template>
  <div class="result">
<h4 @click="setActive">{{songData.trackName}} - {{songData.collectionName}}</h4>
<img :src="songData.artworkUrl100">
  </div>
</template>

<script>
  export default {
    name: 'result',
    props: ['songData', 'setActiveCB'],
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
