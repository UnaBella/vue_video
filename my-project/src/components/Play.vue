<template>
  <div class="play">
    <div class="top">
      <div class="video">
        <img src="../assets/img/P1.png" alt="">
      </div>
      <div class="txt">
        <div class="title">
          <p>{{word}}</p >
        </div>
        <div class="content">
          <p>Nutricia Aptamil 金装爱他美澳洲畅销奶粉品牌，来自新西兰纯净奶源，原料天然，无蔗糖，无香精，口感清淡，宝贝喜爱。特添加益生元组合，有助于改善肠道环境，为宝宝的健康成长提供科学的支持。</p >
        </div>
        <div class="time">
          <p>{{id}}</p >
        </div>
      </div>
    </div>
    <div class="list-item">
      <ul class="clearfix">
        <li>
          <div class="img">
            <a href="">
              <img class="lazy" src="../assets/img/L2.png" />
            </a >
          </div>
          <div class="txt">
            <h3>Aptamil  Gold 金装爱他美2段  6-12个月 900g</h3>
            <div class="price">
              <span>¥100.00</span>
            </div>
          </div>
       
        </li>
        <li>
          <div class="img">
            <a href="">
              <img class="lazy" src="../assets/img/L2.png" />
            </a >
          </div>
          <div class="txt">
            <h3>Aptamil  Gold 金装爱他美2段  6-12个月 900g</h3>
            <div class="price">
              <span>¥100.00</span>
            </div>
          </div>
         
        </li>
        <li>
          <div class="img">
            <a href="">
              <img class="lazy" src="../assets/img/L2.png" />
            </a >
          </div>
          <div class="txt">
            <h3>Aptamil  Gold 金装爱他美2段  6-12个月 900g</h3>
            <div class="price">
              <span>¥100.00</span>
            </div>
          </div>
         
        </li>
        <li>
          <div class="img">
            <a href="">
              <img class="lazy" src="../assets/img/L2.png" />
            </a >
          </div>
          <div class="txt">
            <h3>Aptamil  Gold 金装爱他美2段  6-12个月 900g</h3>
            <div class="price">
              <span>¥100.00</span>
            </div>
          </div>
          
        </li>
      </ul>
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
      id:"",
      word:"ppppp"
    }
  },
  created() {
    this.id = this.$route.query.id;
  },
  mounted:function () {
    axios.get("http://localhost:8080/static/test.json",{
      params: {
        id: this.id,
      }
    }).then(response => {
        console.log(response.data.play)

        // this.itemList = response.data.item;
        this.word = response.data.play.playcon;
        // console.log(this.itemList)
    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
    .play{
  .top{
    width: 375px;
    position:relative;
    text-align: center;
  .video{
    width: 100%;

    img{
      width: 100%;
      max-height: 180px;
    }
  }
  .txt{
    padding: 15px;
    .title{
      display: inline;
      height: 20px;
      font-size: 17px;
      font-weight: 600;
      line-height: 20px;
      color: #fff;
      text-align: left;
      overflow: hidden;
    }
  .content{
    font-size: 12px;
    height: 20px;
    line-height: 20px;
    color: #e1e1e1;
    text-align: left;
    display: inline;
    overflow: hidden;
  }
  .time{
    font-size: 12px;
    height: 20px;
    line-height: 20px;
    color: #7d7d7d;
    text-align: left;
    display: inline;
    overflow: hidden;
  }
  }
  }
  }

  .list-item{
    padding: 25px;
  li {
    overflow: hidden;
    position: relative;
    float: left;
    width: calc(100% / 2);
    border-bottom: 1px solid #b5b5b5;
  .img {
    height: 150px;
    img {
    width: 100%;
    height: 100%
    }
  }
  .txt {
    padding: 5px;
    h3 {
    display: -webkit-box;
    height: 30px;
    line-height: 15px;
    font-size: 13px;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    text-align: center;
    color: #fff;
    overflow: hidden;
    }
  .price {
    position: relative;
    height: 30px;
    line-height: 30px;
    font-size: 13px;
    text-align: center;
    color: #fff;
    margin: 5px 0;
  }
  }
  }
  li:nth-child(2n){
    float: right;
    border-left: 1px solid #b5b5b5;
  }
  }
</style>
