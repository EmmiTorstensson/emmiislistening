<template>
  <div>
    <div id="background-section-1">
      <nuxt-link
          to="/auth"
          name="auth"
          :aria-current="ariaCurrent"
        >Login</nuxt-link>
    </div>
    <div id="background-section-2">

    </div>
    <div class="content">
      <nuxt/>
    </div>
  </div>
</template>

<script>
    export default {
      titleShort: 'is Listening',
      authorName: 'Emmi',
      computed: {
        ariaCurrent() {
          return 'auth' === this.$route.name ? 'page' : false
        }
      },
      head() {
        return {
          title: `${this.$options.authorName} ${
            this.$options.titleShort
          } ·X· A Musical App`
        }
      }
    }
</script>

<style>
    :root {
      --colorGray: #333642;
      --colorBlue: rgba(118, 120, 224, 0.5);
      --colorBrightBlue: rgb(0, 112, 255);
    }

    html {
      background: #fb3120;
    }

    #background-section-1 {
      position: fixed;
      top: 0px;
      left: 0px;
      width: 100%;
      height: 50%;
      background-color: #b4f3c3;
      z-index: 1;
    }

    #background-section-2 {
      position: relative;
      z-index: 2;
      padding: 30px;
      text-align: center;
      top: 0;
    }

    .content {
      position: relative;
      z-index: 3;
      margin: 0;
      padding: 0;
    }

    body {
      padding: 0;
      margin: 0;
      color: #b4f3c3;
      font-family: 'Montserrat', sans-serif;
    }

    a {
      color: white;
      text-decoration: none;
      display: inline-block;
      position: relative;
    }

    a:after,
    a:before {
      content: '';
      position: absolute;
      left: 0;
      right: 0;
      height: 1em;
      z-index: -1;
      mix-blend-mode: color-burn;
    }

    a:after {
      bottom: 2px;
      background: var(--colorBlue);
      z-index: -1;
      transform: rotate(-3deg);
    }

    a:before {
      background: rgba(118, 120, 224, 0.4);
      transform: rotate(2deg);
    }

    .nuxt-progress {
      opacity: 0.3;
      height: 2px;
      bottom: 0;
      top: auto;
    }
</style>