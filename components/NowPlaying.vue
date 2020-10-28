<template>
    <div>
        <h1>{{name}}</h1>
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
        artistList
    }
    
}
</script>