<template>
    <div class="inner-container">

        <img    v-if="image" 
                :src="image" 
                alt="Album Artwork" 
                class="album-cover"
        >

        <h2 class="track-name">{{name}}</h2>
        <p class="artist-name">{{artistsList}}</p>
        <a v-if="href" :href="href">Listen?</a>
    </div>
    
</template>

<script>
export default {
    props: ['isPlaying', 'nowPlaying'],

    data() {
        return {
            hovered: false
        }
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
        artistsList() {
            const { artists } = this.nowPlaying
            return artists ? artists.map(artist => artist.name).join(', ') : null
        },
        name() {
            return this.nowPlaying.name
        },
        href() {
            const { external_urls } = this.nowPlaying
            return external_urls ? external_urls.spotify : null
        },

    }
    
}
</script>

<style scoped>
    .inner-container {
        height: 100%;
        color: #b4f3c3;
    }

    .album-cover {
        max-width: 60%;
        height: auto;
        box-shadow: 0 1px 1px rgba(0,0,0,0.15), 
                    0 2px 2px rgba(0,0,0,0.15), 
                    0 4px 4px rgba(0,0,0,0.15), 
                    0 8px 8px rgba(0,0,0,0.15);
    }

    .track-name {
        line-height: 1.2;
        font-size: 2.5rem;
        margin: 0;
    }

    .artist-name {
        font-size: 1rem;
        margin: 0;
    }
</style>