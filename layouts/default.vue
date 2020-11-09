<template>
  <div class="main-wrapper">

    <Header :isAuth="isAuth"/>

    <div class="nuxt-mount">
      <nuxt/>
    </div>
    
    <div class="nuxt-link">
      <nuxt-link
        to="/auth"
        name="auth"
        :aria-current="ariaCurrent"
        >Login</nuxt-link>
    </div>
  </div>
</template>

<script>
import Header from '~/components/Header.vue';

export default {

  components: { Header },
  titleShort: 'is Listening',
  authorName: 'Emmi',
  computed: {
    isAuth() {
      return this.$route.name === 'auth'
    },
    ariaCurrent() {
      return this.isAuth ? 'page' : false
    },
    rootClass() {
      return this.isAuth ? 'auth base' : 'base'
    }
  },
  head() {
    return {
      title: `${this.$options.authorName} ${
        this.$options.titleShort
      } ·X· A Musical App`,
      link: [
        {
          rel: 'stylesheet',
        }
      ]
    }
  }
} 
</script>

<style>

    html {
      background: linear-gradient(to bottom, #b4f3c3 50%, #ff0000 50%);
      min-height: 100%;
      font-size: 100%;
    }

    body {
      padding: 0;
      margin: 0;
      color: white;
      font-family: 'Montserrat', sans-serif;
    }

    .main-wrapper{
      min-height: 100vh;
    }

    .nuxt-link {
      position: absolute;
      top: 0;
      left: 0;
    }

    a {
      color: white;
      text-decoration: none;
      display: inline-block;
      position: relative;
    }


</style>