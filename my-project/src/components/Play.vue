<template>
  <div class="play">
    <h1>{{ msg }}</h1>
    <h2>play</h2>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
  .play{
    border: 1px solid red;
    h1{
      color: yellow;
    }
  }
</style>
