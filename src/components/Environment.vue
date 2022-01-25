<template>
  <div class="all">
    <div class="top">
      <div class="left">
      </div>
      <div class="right">
        <div class="right_inside">
          <div class="topic_title">環境介紹</div>
          <div class="topic_eng">Service</div>
          <div class="title_line"></div>
          <p>位於南陽路鄰近豐原大道，交通便利，有廣大的前庭位置，停車方便。</p>
        </div>
      </div>
    </div>
    <div class="area">
      <div class="tag">
        <span class="tag_circle">
          <img src="./../assets/img/CloseUp.svg" />
        </span>
        <span class="description">戶外休閒區</span>
      </div>
      <div class="pic_set">
        <img src="./../assets/environment/environment_outdoor1.jpg" />
        <img src="./../assets/environment/environment_indoor3.jpg" />
        <img src="./../assets/environment/environment_outdoor3.jpg" />
      </div>
      <div class="content">
        <p style="text-align: justify;">房舍外有步道，周圍有種植花草，供住民平時活動、日光浴，慢活樂趣。</p>
      </div>
    </div>
    <div class="area">
      <div class="tag">
        <span class="tag_circle">
          <img src="./../assets/img/bi_house-door-fill.svg" />
        </span>
        <span class="description">院內環境</span>
      </div>
      <div class="indoor_content">
        <div class="indoor_column">
          <div class="indoor_pic_set">
            <img src="./../assets/environment/environment_indoor2.jpg" />
            <img src="./../assets/environment/environment_indoor10.jpg" />
          </div>
          <div class="indoor_text">
            <div class="title">休閒交誼廳</div>
            <div class="line"></div>
            <p>走廊光明清幽、中庭擺設電視，提供住民休閒娛樂。</p>
          </div>
        </div>
        <div class="indoor_column">
          <div class="indoor_pic_set">
            <img src="./../assets/environment/environment_119_1.jpg" />
            <img src="./../assets/environment/environment_119_2.jpg" />
          </div>
          <div class="indoor_text">
            <div class="title">消防疏散避難系統</div>
            <div class="line"></div>
            <p>設有自動灑水設備、119自動通報系統，讓行動不便長輩多一層保障。</p>
          </div>
        </div>
        <div class="indoor_column">
          <div class="indoor_pic_set">
            <img src="./../assets/environment/environment_bathroom2.jpg" />
            <img src="./../assets/environment/environment_bathroom1.jpg" />
          </div>
          <div class="indoor_text">
            <div class="title">護理服務設施－盥洗區</div>
            <div class="line"></div>
            <p>設有無障礙盥洗空間，讓長輩可以更方便、安全地清潔。</p>
          </div>
        </div>
      </div>
    </div>
    <div class="area">
      <div class="tag">
        <span class="tag_circle">
          <img src="./../assets/img/Insomnia.svg" />
        </span>
        <span class="description">寢室環境</span>
      </div>
      <div class="pic_set">
        <img src="./../assets/environment/environment_indoor9.jpg" />
        <img src="./../assets/environment/environment_indoor7.jpg" />
        <img src="./../assets/environment/environment_bed.jpg" />
      </div>
      <div class="content">
        <p style="text-align: justify;">寢室格局有雙人房、六人房，皆有獨立廁所、冷氣，配備床、床旁桌、頭燈、圍簾，以及個人獨立衣櫥，收納空間相當充足。</p>
      </div>
    </div>
  </div>
</template>
<script>
import dataset from '../assets/data.json'
const data = dataset.objectives
export default {
  name: 'environment',
  data () {
    return {
      data: data
    }
  },
  props: {
    msg2: String
  }
}

</script>
<style scoped>
.all .top {
  margin-top: 5px;
  display: flex;
  width: 100%;
  height: 480px;
}
.all .left {
  width: 50%;
  height: 100%;
  background-image: url('../assets/environment/environment_door2.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 0 -10px;
  background-color: #eee;
}
.all .right {
  width: 50%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.all .right .right_inside {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 75%;
}
.all .right .right_inside p {
  font-size: 24px;
  line-height: 28px;
  color: #2C2C2C;
  margin-top: 60px;

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
.all {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-bottom: 58px;
}
.area {
  width: 80%;
}
.tag{
  width: 300px;
  border-radius: 99px;
  background-color: #CAE9BE;
  display: flex;
  align-items: center;
  column-gap: 32px;
  padding: 5px 48px 5px 5px;
  margin-top: 72px;
  margin-bottom: 40px;
}
.tag_circle{
  background-color: #ffffff;
  width: 45px;
  height: 45px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
}
.description{
  font-size: 18px;
  font-weight: bold;
  line-height: 100%;
  line-height: 21px;
  color: #2C2C2C;
}
.content{
  display: flex;
  align-items: center;
  justify-content: center;
  column-gap: 28px;
  border-top: 1px solid #acacac;
  border-bottom: 1px solid #acacac;
  padding: 36px 28px;
  font-size: 18px;
  line-height: 21px;
  color: #2C2C2C;
  margin-top: 48px;
}
.pic_set {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  column-gap: 12px;
}
.pic_set img {
  width: 32%;
}
.indoor_content {
  display: flex;
  flex-direction: column;
  row-gap: 36px;
}
.title {
  font-size: 24px;
  font-weight: bold;
  line-height: 28px;
  color: #29471c;
}
.line {
  height: 4px;
  width: 58px;
  background-color: #29471c;
}
.indoor_column {
  display: flex;
}
.indoor_column .indoor_text {
  width: 70%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  row-gap: 16px;
  padding: 5px 2%;
}
.indoor_column .indoor_text p {
  font-size: 18px;
}
.indoor_column .indoor_pic_set {
  width: 75%;
}
.indoor_column .indoor_pic_set img{
  width: 50%;
}
@media screen and (max-width: 768px) {
  .all .top {
    flex-direction: column;
    height: 500px;
  }
  .all .left {
    width: 100%;
  }
  .all .right {
    width: 100%;
  }
  .all .right .right_inside {
    margin-top: 24px;
  }
  .content {
    margin: 24px 20px 0px 20px;
  }
}
@media only screen and (max-width: 480px) {
  .area {
    width: 100%;
  }
  .topic_title {
    font-size: 30px;
  }
  .topic_eng {
    font-size: 20px;
  }
  .all .right .right_inside p {
    font-size: 16px;
    margin-top: 12px;
  }
  .tag {
    width: 90%;
    margin: 20px auto 12px auto;
  }
  .pic_set{
    flex-direction: column;
  }
  .pic_set img {
    width: 80%;
    padding: 10px;
  }
  .indoor_column {
    align-items: center;
    flex-direction: column;
  }
  .indoor_column .indoor_text {
    margin-top: 10px;
  }
  .indoor_column .indoor_pic_set {
    width: 85%;
  }
  .indoor_column .indoor_pic_set img{
    width: 50%;
  }
  .line {
    width: 50%;
    background-color: #29471c;
  }
  .area .content p {
    font-size: 16px;
  }
  .indoor_column .indoor_text p {
    font-size: 16px;
  }
  .content {
    margin: 16px 12px 0px 12px;
    padding: 24px 20px;
  }
  .title {
    font-size: 20px;
  }
}
</style>
