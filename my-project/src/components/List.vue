<template>
  <div class="list">
      <div class="top">
        <div class="image"></div>
        <div class="filter"></div>
        <div class="des">
            <h2>美姿</h2>
            <p>仪态、站立及走路的姿势</p>
        </div>
      </div>
      <div class="other">

      
        <div class="unit" v-for="(item,index) in itemList" v-bind:key="index">
          <router-link :to="{path:'/play',query: {id:item.id}}">
            <div class="left">
              <img src="../assets/img/L1.png" alt="">
            </div>
            <div class="right">
              <div class="f14">{{item.name}}</div>
              <p class="mt55">1028/01/30</p>
              <p>主讲人: 东 优妃</p>
            </div>
          </router-link>
        </div>

        <!-- <div class="unit">
          <div class="left">
            <img src="../assets/img/L1.png" alt="">
          </div>
          <div class="right">
            <div class="f14">你的饮食习惯正确吗?10个容易忽视的餐桌健康小问题</div>
            <p class="mt55">1028/01/30</p>
            <p>主讲人: 东 优妃</p>
          </div>
        </div> -->


      </div>
    <!-- <router-link to="/play">
      <div class="toPlay">
        {{$route.params.id}}
      </div>
    </router-link> -->
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      itemList : []
    }
  },
  created() {
    console.log('1');
  },
  mounted:function () {
    axios.get("http://localhost:8080/static/test.json")
      .then(response => {
        console.log(response)
      this.itemList = response.data.item
        console.log(this.itemList)
      });

    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
  .list{
    .top{
      width: 375px;
      height: 180px;
      position:relative;
      text-align: center;
      .image{
        width:100%;
        height:100%;
        background: url(../assets/img/L1.png) no-repeat 0 0 ;
        background-size: 100% 100%;

      }
      .filter{
        position: absolute;
        top: 0;
        width:100%;
        height:99%;
        background: url(../assets/img/L1.png) no-repeat 0 0 ;
        background-size: 100% 99%;
        filter:blur(2px);
      }
      .des{
        background: rgba(0, 0, 0, 0.2);
        position:absolute;
        top: 0;
        width: 375px;
        height: 180px;
        color: #fff;
        padding-top: 45px;
        h2{
          font-size: 50px;
        }
        p{
          font-size:16px;
        }
      }
    }
    .other{
      padding: 12px 12px;
      .unit{
        overflow: hidden;
        padding: 5px;
        background: #1b1a1b;
        border-radius: 8px;
        margin: 10px 0;
        .left{
          float: left;
          width:90px;
          height:140px;

          // border: 1px solid red;
          img{
            width:100%;
            height:100%;
            border-radius:8px;
          }
        }
        .right{
          color:#fff;
          float: right;
          width:250px;
          height:140px;
          padding:6px 10px;
          p{
            color: #afafaf;
          }
        }
      }


    }
  }
</style>
