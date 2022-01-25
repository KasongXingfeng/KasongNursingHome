<template>
  <div class="activities">
    <div class="activities_top">
      <div class="topic_title">活動花絮</div>
      <div class="topic_eng">activities</div>
      <div class="title_line"></div>
    </div>
    <div class="activities_content">
      <div class="card" v-for="item in data.slice((nowPage - 1)*6,(nowPage - 1)*6 + 6)" :key="item">
        <div>
          <img class="picture" v-bind:src="require('./../assets/activity/' + item.picture + '.jpg')" />
        </div>
        <div class="title">{{item.title}}</div>
        <div class="line"></div>
      </div>
    </div>
    <div class="pagination">
      <img style="padding-right: 28px" src="./../assets/img/Back.svg" v-on:click="prev"/>
      <span class="page" v-for="(page,index) in totalPage" :key="index+1" v-bind:class="[nowPage==index+1?'selected':'unselected']" v-on:click="selectedPage(index+1)">{{index + 1}}</span>
      <img style="padding-left: 28px" src="./../assets/img/Forward.svg" v-on:click="next"/>
    </div>
  </div>
</template>
<script>
import dataset from '../assets/data.json'
const data = dataset.activities
let totalPage = parseInt(data.length / 6)
if (data.length % 6 !== 0) {
  totalPage = totalPage + 1
}
const nowPage = 1
export default {
  name: 'Activities',
  data () {
    return {
      data: data,
      totalPage: totalPage,
      nowPage: nowPage
    }
  },
  methods: {
    selectedPage: function (index) {
      this.nowPage = index
    },
    next: function () {
      if (this.nowPage !== this.totalPage) {
        this.nowPage = this.nowPage + 1
      }
    },
    prev: function () {
      if (this.nowPage !== 1) {
        this.nowPage = this.nowPage - 1
      }
    }
  },
  props: {
    msg2: String
  }
}

</script>
<style scoped>
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
.activities {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.activities .activities_top {
  width: 60%;
  margin: 72px 50px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.activities_content{
  width: 60%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  row-gap: 24px;
}
.activities_content .card{
  background-color: #fff;
  width: 32%;
  padding: 18px 0;
  height: 400px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-direction: column;
  /* row-gap: 2px; */
  border: solid 1px #eee;
  box-shadow: 2px 4px 6px rgba(0, 0, 0, 0.25);
}
.activities_content .card .picture{
  width: 90%;
  height: 90%;
  /* background-color: #ddd; */
}
.activities_content .card .title{
  font-size: 24px;
  line-height: 28px;
  color: #2c2c2c;
}
.activities_content .card .line{
  width: 90px;
  height: 1px;
  background-color: #29471C;
}
.pagination{
  background-color: #fff;
  border: 2px solid #CAE9BE;
  box-sizing: border-box;
  border-radius: 99px;
  padding: 18px;
  display: flex;
  align-items: center;
  justify-content: center;
  column-gap: 8px;
  margin: 58px 0;
}

.pagination .page{
  width: 30px;
  height: 30px;
  font-size: 18px;
  line-height: 21px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.unselected {
  color: #2c2c2c;
}
.selected {
  font-size: 18px;
  color: #ffffff;
  background-color: #578369;
  border-radius: 50%;
  width: 30px;
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
}
@media screen and (max-width: 1440px) {
.activities .activities_top {
    width: 80%;
  }
  .activities_content {
    width: 80%;
  }
}
@media only screen and (max-width: 1024px) {
  .activities_content .card{
    width: 46%;
    height: 340px;
  }
  .activities_content .card .picture{
    width: 92%;
    height: 100%;
    /* background-color: #ddd; */
  }
}
@media only screen and (max-width: 480px) {
  .activities .activities_top {
    /* margin: ; */
  }
  .activities_content .card{
    width: 100%;
  }
  .topic_title {
    font-size: 30px;
  }
  .topic_eng {
    font-size: 20px;
  }
  .activities_content .card .title {
    font-size: 20px;
  }
}
</style>
