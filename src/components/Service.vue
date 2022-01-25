<template>
  <section>
    <div v-for="(item,index) in introduction" :key="item">
      <div class="service_top" v-if="index==nowPic">
        <!-- <div class="left" style="background-image: url('./../activity/activity_birthday.jpg');"> -->
        <div class="left">
          <img class="picture" v-bind:src="require('./../assets/service/' + item.picture + '.jpg')" />
        </div>
        <div class="right">
          <div></div>
          <p class="title">{{item.title}}</p>
          <div class="dots">
            <span class="dot" v-for="(item,index) in introduction" :key="item" v-on:click="selectPic(index)" v-bind:class="[nowPic==index?'selected':'unselected']"></span>
          </div>
        </div>
      </div>
    </div>
  </section>
  <div class="client">
    <div class="client_top">
      <div class="topic_title">服務對象</div>
      <div class="topic_eng">Client</div>
      <div class="title_line"></div>
    </div>
    <div class="client_content">
      <div class="columns" id="app">
        <div class="column" v-for="item in client" :key="item">
          <span class="client_circle">
            <img src="./../assets/img/carbon_airline-passenger-care.svg">
          </span>
          <span class="description">{{ item.content }}</span>
        </div>
      </div>
    </div>
  </div>
    <div class="charges">
    <div class="charges_top">
      <div class="topic_title">收費標準</div>
      <div class="topic_eng">charges</div>
      <div class="title_line"></div>
    </div>
    <div class="charges_content">
      <div class="box" v-for="item in charges" :key="item">
        <div class="tag">
          <span class="tag_circle">
            <img v-bind:src="require('./../assets/img/' + item.icon + '.svg')" />
          </span>
          <span class="description">{{ item.charge }}</span>
        </div>
        <div class="box_inside">
          <div class="detail" v-for="detail in item.charge_item" :key="detail">
            <span class="detail_name">{{detail.item_name}}</span>
            <span class="detail_price">{{detail.price}}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import dataset from '../assets/data.json'
import { setInterval } from 'timers'
const introduction = dataset.services
const client = dataset.client
const charges = dataset.charges
const nowPic = 0
export default {
  name: 'service',
  data () {
    return {
      client: client,
      charges: charges,
      introduction: introduction,
      nowPic: nowPic,
      timer: 0
    }
  },
  created () {
    this.timer = setInterval(() => {
      if (this.nowPic >= 8) {
        this.nowPic = 0
      } else {
        console.log(this.nowPic)
        this.nowPic += 1
      }
      // 定時器的回撥函式中需要注意 this 指向
    }, 5000)
  },
  methods: {
    selectPic: function (index) {
      this.nowPic = index
    }
  },
  props: {
    msg2: String
  }
}

</script>
<style scoped>
.service_top {
  width: 100%;
  display: flex;
}
.service_top .left {
  width: 50%;
  height: 600px;
  background-color: #eee;
}
.service_top .left .picture {
  height: 100%;
  width: 100%;
}
.service_top .right {
  width: 50%;
  height: auto;
  background-color: #f0fcea;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  /* padding: 10px; */
}
.service_top .right .title {
  font-size: 25px;
  line-height: 28px;
  color: #2C2C2C;
}
.service_top .right .dots {
  display: flex;
  column-gap: 12px;
}
.service_top .right .dot {
  border-radius: 50%;
  width: 12px;
  height: 12px;
  cursor: pointer;
}
.topic_title {
  font-size: 32px;
  font-weight: bold;
  line-height: 37px;
  color: #29471c;
  margin-bottom: 4px;
}
.topic_eng {
  font-size: 24px;
  font-weight: bold;
  line-height: 28px;
  color: #805800;
  margin-bottom: 10px;
}
.title_line{
  height: 2px;
  width: 58px;
  background-color: #29471c;
}
.selected {
  background-color: #578369;
}
.unselected {
  background-color: #c4c4c4;
}
.client {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.client .client_top {
  width: 60%;
  margin: 60px 50px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.client_content {
  width: 60%;
}
.client_content .columns {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  row-gap: 24px;
}
.client_content .column {
  width: 47%;
  border-radius: 99px;
  background-color: #CAE9BE;
  display: flex;
  align-items: center;
  column-gap: 12px;
  padding: 5px;
}
.client_content .client_circle{
  background-color: #ffffff;
  width: 45px;
  height: 45px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
}
.client_content .description{
  font-size: 18px;
  line-height: 21px;
  /* padding: 5px 0; */
  color: #2C2C2C;
}
.charges {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.charges .charges_top {
  width: 60%;
  margin: 60px 42px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.charges_content {
  width: 60%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-bottom: 84px;
  row-gap: 42px;
}
.charges_content .box{
  height: 316px;
  border: solid 1px #ACACAC;
  width: 47%;
  border-radius: 8px;
  display: flex;
  flex-direction: column;
  align-items: center;
  row-gap: 24px;
}
.charges_content .box .tag{
  /* width: 220px; */
  border-radius: 99px;
  background-color: #CAE9BE;
  display: flex;
  align-items: center;
  column-gap: 32px;
  padding: 5px 48px 5px 5px;
  margin-top: 24px;
}
.charges_content .tag_circle{
  background-color: #ffffff;
  width: 45px;
  height: 45px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
}
.charges_content .description{
  font-size: 18px;
  font-weight: bold;
  line-height: 100%;
  line-height: 21px;
  color: #2C2C2C;
}
.charges_content .box_inside{
  width: 60%;
}
.charges_content .box_inside .detail{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.charges_content .box_inside .detail .detail_name{
  font-weight: 500;
  font-size: 18px;
  line-height: 28px;
  color: #2C2C2C;
}
.charges_content .box_inside .detail .detail_price{
  font-weight: 500;
  font-size: 18px;
  line-height: 100%;
  color: #805800;
}
.client_content .client_circle img{
    width: 32px;
}
@media only screen and (max-width: 1440px) {
  .client .client_top {
      width: 75%;
  }
  .client_content {
    width: 75%;
  }
  .charges .charges_top {
    width: 75%;
  }
  .charges_content {
    width: 75%;
  }
  .charges_content .box_inside{
    width: 75%;
  }
  .service_top .left {
    width: 50%;
    height: 700px;
  }
}
@media only screen and (max-width: 1024px) {
  .service_top .right .title {
    font-size: 12px;
  }
  .client_content .columns {
    flex-direction: column;
  }
  .client_content .column {
    width: auto;
  }
  .charges_content {
    flex-direction: column;
    margin-bottom: 48px;
  }
  .charges_content .box {
    width: auto;
    height: auto;
  }
  .charges_content .box_inside .detail .detail_name {
    font-size: 16px;
  }
  .charges_content .box_inside .detail .detail_price {
    font-size: 16px;
  }
}
@media only screen and (max-width: 768px) {
  .client_content {
    width: 90%;
  }
  .charges_content {
    width: 90%;
  }
  .service_top {
    flex-direction: column;
  }
  .service_top .right {
    width: 100%;
    padding: 32px 24px;
  }
  .client_content .client_circle {
    width: 30px;
    height: 30px;
  }
  .client_content .client_circle img{
    width: 20px;
  }
  .client_content .columns {
    row-gap: 20px;
  }
  .service_top .left {
    width: 100%;
    height: 450px;
  }
}
  @media only screen and (max-width: 480px) {
  .charges_content .box_inside {
    width: 80%;
  }
  .client_content .description {
    font-size: 12px;
  }
  .topic_title {
    font-size: 30px;
  }
  .topic_eng {
    font-size: 20px;
  }
  .service_top .left {
    width: 100%;
    height: 350px;
  }
}
</style>
