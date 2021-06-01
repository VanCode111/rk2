<template>
  <Home/>
</template>

<script>
import Home from './views/Home';

export default {
  components: {
    Home
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Ubuntu:wght@500&display=swap');
  *{
    box-sizing: border-box;
  }
  body{
    margin: 0;
    padding: 0;
    min-width: 320px;
    font-family: 'Ubuntu', sans-serif;
  }
</style>
