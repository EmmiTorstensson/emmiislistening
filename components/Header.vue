<template>
  <header>
    <h1>
      {{$nuxt.layout && $nuxt.layout.authorName}} {{ $nuxt.layout && $nuxt.layout.titleShort }}
      <nuxt-link to="/auth" name="auth" aria-label="Login" :aria-current="isAuth"/>
    </h1>
  </header>
</template>

<script>
    export default {
        props: ['isAuth']
    }
</script>

<style scoped>
    header h1{
        color: hotpink;
    }
</style>