<template>
  <div class = "all">
    <div class="cover">
      <div class="title">關於佳松</div>
      <div class="line"></div>
      <div class="subtitle">專業化、人性化，有尊嚴的關懷與照顧。</div>
    </div>
    <div class="concept">
      <div class="concept_top">
        <div class="topic_title">服務理念</div>
        <div class="topic_eng">Service Concept</div>
        <div class="title_line"></div>
      </div>
      <div class="concept_content">
        <div class="column">
          <span class="title">全心</span>
          <span class="subtitle">愛心、耐心、貼心、安心、放心。</span>
        </div>
        <div class="column">
          <span class="title">全意</span>
          <span class="subtitle">讓顧客滿意、員工得意、全體如意。</span>
        </div>
      </div>
    </div>
    <div class="objectives">
      <div class="objectives_top">
        <div class="topic_title">服務目標</div>
        <div class="topic_eng">Service Objectives</div>
        <div class="title_line"></div>
      </div>
    <div class="objectives_content">
      <div class="columns" id="app">
        <div class="column" v-for="(item,index) in data" :key="item">
          <span class="index_circle">
            <span class="index">{{ index+1 }}</span>
          </span>
          <span class="description">{{ item.objective }}</span>
        </div>
      </div>
    </div>
    </div>
    <div class="conclusion">
      <div class="conclusion_content">
        <div>
          <img src="./../assets/img/carbon_airline-passenger-care.svg">
        </div>
        <p>每位需要被照顧服務者都是我們心中的寶貝，即使身體失能了、記憶力衰退了，還是值得被好好的照顧與關懷，佳松護理之家秉持用心照護，讓家屬安心托護，一起為被照顧服務者提供完善的生活品質！</p>
      </div>
    </div>
  </div>
</template>

<script>
import dataset from '../assets/data.json'
const data = dataset.objectives
export default {
  name: 'Homepage',
  data () {
    return {
      data: data
    }
  },
  props: {
    msg: String
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.all .cover {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 300px;
  width: 100%;
  background-image: url('../assets/img/unsplash_VUOiQW4OeLIcover.png');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center center;
}
.all .cover .title {
  color: #29471c;
  font-size: 48px;
  line-height: 56px;
  font-weight: bold;
}
.all .cover .line {
  background-color: #29471c;
  height: 2px;
  width: 58px;
  margin: 12px 0 20px;
}
.all .cover .subtitle {
  color: #2c2c2c;
  font-size: 18px;
  line-height: 21px;
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
.all .concept {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.all .concept .concept_top {
  width: 60%;
  margin: 102px 50px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.all .objectives {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-bottom: 82px;
}
.all .objectives .objectives_top {
  width: 60%;
  margin: 102px 50px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.all .concept .column {
  display: flex;
  align-items: center;
  column-gap: 38px;
  margin-bottom: 24px;
}
.all .concept .concept_content .title{
  padding: 12px 56px;
  border: solid 2px #cae9be;
  border-radius: 99px;
  box-sizing: border-box;
  font-size: 24px;
  line-height: 28px;
  color: #2C2C2C;
}
.all .concept .concept_content .subtitle{
  font-size: 18px;
  line-height: 21px;
  color: #2C2C2C;
}
.all .objectives_content {
  width: 60%;
}
.all .objectives_content .columns {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  row-gap: 24px;
}
.all .objectives_content .column {
  width: 47%;
  border-radius: 99px;
  background-color: #CAE9BE;
  display: flex;
  align-items: center;
  column-gap: 12px;
  padding: 5px;
}
.all .objectives_content .index_circle{
  background-color: #ffffff;
  width: 45px;
  height: 45px;
  border-radius: 50%;
}
.all .objectives_content .index{
  font-weight: bold;
  font-size: 24px;
  line-height: 45px;
  color: #888888;
}
.all .objectives_content .description{
  font-size: 18px;
  line-height: 21px;
  /* padding: 5px 0; */
  color: #2C2C2C;
}
.conclusion {
  display: flex;
  justify-content: center;
  margin-bottom: 82px;
}
.conclusion .conclusion_content {
  width: 54%;
  display: flex;
  align-items: center;
  column-gap: 28px;
  border-top: 1px solid #acacac;
  border-bottom: 1px solid #acacac;
  padding: 36px 28px;
  font-size: 18px;
  line-height: 21px;
  color: #2C2C2C;
}
.conclusion .conclusion_content p{
  color: #2c2c2c;
  font-size: 18px;
  line-height: 21px;
}
@media screen and (max-width: 1440px){
  .all .concept .concept_top {
    width: 80%;
  }
  .all .objectives .objectives_top {
    width: 80%;
    margin: 102px 50px;
  }
  .all .objectives_content {
    width: 80%;
  }
  .conclusion .conclusion_content {
    width: 70%;
  }
}
@media screen and (max-width: 1024px){
  .all .concept .concept_top {
    margin: 60px 50px;
  }
  .all .concept .column{
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .all .concept .concept_content .title{
    margin-bottom: 35px;
    font-size: 20px;
    line-height: 24px;
  }
  .all .concept .concept_content .subtitle{
    font-size: 18px;
    line-height: 20px;
  }
  .all .objectives .objectives_top {
    margin: 60px 50px;
  }
  .all .objectives_content .description {
    font-size: 16px;
    line-height: 30px;
  }
  .conclusion .conclusion_content {
    flex-direction: column;
    font-size: 16px;
    line-height: 20px;
  }
  .conclusion {
    margin-bottom: 72px;
  }
  .all .objectives {
    margin-bottom: 72px;
  }
  .all .objectives_content .columns {
    display: flex;
    justify-content: space-around;
    row-gap: 24px;
  }
  .all .objectives_content .column {
    width: 100%;
    column-gap: 8px;
  }
}
@media screen and (max-width: 768px){
  .all .cover .subtitle {
    font-size: 16px;
  }
  .all .objectives_content {
    width: 90%;
  }
  .all .objectives_content .index_circle {
    width: 30px;
    height: 30px;
  }
  .all .objectives_content .index_circle {
    width: 30px;
    height: 30px;
  }
  .all .objectives_content .index {
    line-height: 30px;
    font-size: 18px
  }

  .conclusion .conclusion_content {
    padding: 20px;
  }
  .conclusion {
    margin-bottom: 48px;
  }
  .conclusion .conclusion_content p {
    font-size: 14px;
  }
}
@media screen and (max-width: 480px) {
  .all .cover .title {
    font-size: 36px;
  }
  .all .objectives_content .description {
    font-size: 12px;
  }
  .conclusion .conclusion_content p {
    font-size: 12px;
  }
  .topic_title {
    font-size: 30px;
  }
  .topic_eng {
    font-size: 20px;
  }
}
</style>
