<template>
    <div class="results row">
        <div class="col">
            <h2>Results: {{results.length}}</h2>
        </div>
        <div class="row">
            <result v-for="(res) in results" class="col-12" :setActiveCB="setActive" :class="{active: res.trackName == previewedSong}"
                :songData="res">
            </result>
        </div>
    </div>
</template>

<script>
import Result from '@/components/Result.vue'
export default {
    name: 'results',
    data() {
        return {
            previewedSong: ''
        }
    },
    methods: {
        setActive(song) {
            this.previewedSong = song.trackName
        }
    },
    computed: {
        results() {
            return this.$store.state.searchResults
        }
    },
    components: {
        Result
    }
}

</script>

<style>
.results {
    background: blue
}


</style>