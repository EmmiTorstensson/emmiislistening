<template>
    <div>
        <img v-if="image" :src="image" alt="Album Artwork" class="album-cover">
        <h2>{{name}}</h2>
    </div>
    
</template>

<script>
import Progress from './Progress.vue'

export default {
    components: { Progress },
    props: ['isPlaying', 'nowPlaying'],
    data() {
        return { staleTimer: '', trackTimer: '' }
    },
    computed: {
        image() {
            const { album, image } = this.nowPlaying
            if (Boolean(album)) {
                const { url } = album.images[0]
                return url
            }
            return Boolean(image)
                ? iamge
                : 'https://developer.spotify.com/assets/branding-guidelines/icon2@2x.png'
        },
        Progress() {
            return this.$store.state.trackProgress
        },
        artistList() {
            const { artist } = this.nowPlaying
            return artist ? artist.map(artist = artsit.name).join(', ') : null
        },
        name() {
            return this.nowPlaying.name
        }
    }
    
}
</script>

<style scoped>
    .album-cover {
        max-width: 60%;
        height: auto; 
    }

</style>