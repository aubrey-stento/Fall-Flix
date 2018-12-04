<template>

    <div class="preview row">
        <div class="col mb-5 mr-10">
            <h2>Preview:</h2>
        </div>

        <div v-if="song.trackName" class="row">
            <div class="col">
                <img :src="song.img"/>
                <audio controls>
                    <source :src='song.previewUrl' />
                </audio>
            </div>
        </div>
    </div>


</template>

<script>
    export default {
        name: 'preview',
        computed: {
            song() {
                return this.$store.state.activeSong
            }
        }
    }
</script>

<style>
    .preview {
        background: pink
    }
</style>