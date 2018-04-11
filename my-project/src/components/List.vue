<template>
  <div class="list">
    <h1>{{ msg }}</h1>
    <h2>list</h2>
    <router-link to="/play">
      <div class="toPlay">
        {{$route.params.id}}
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  created() {
    console.log('1');
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
  .list{
    border: 1px solid green;
    h2{
      color: blue;
    }
    .toPlay{
      width:375px;
      height: 375px;
      border:1px solid yellow;
    }
  }
</style>
