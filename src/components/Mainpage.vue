<template>
  <div class="navbar" v-on:click="closeNav">
    <router-link to="/" style="display: flex; justify-content: flex-start;">
      <img class="picture" src="./../assets/image2.png">
    </router-link>
    <div class="links">
      <router-link to="/orginazation" class="link">組織架構</router-link>
      <span>|</span>
      <router-link to="/service" class="link">服務介紹</router-link>
      <span>|</span>
      <router-link to="/environment" class="link">環境介紹</router-link>
      <span>|</span>
      <router-link to="/activities" class="link">活動花絮</router-link>
    </div>
  </div>
  <div class="links_md" v-on:click="openNav" v-if="!sidebarOpen">
    <img src="./../assets/img/Menu.svg">
  </div>
  <div id="mySidenav" class="sidenav" v-if="sidebarOpen">
    <div class="close">
      <img src="./../assets/img/close.svg" v-on:click="closeNav"/>
    </div>
    <router-link to="/orginazation" class="link" v-on:click="closeNav">組織架構</router-link>
    <router-link to="/service" class="link" v-on:click="closeNav">服務介紹</router-link>
    <router-link to="/environment" class="link" v-on:click="closeNav">環境介紹</router-link>
    <router-link to="/activities" class="link" v-on:click="closeNav">活動花絮</router-link>
  </div>
  <router-view  v-on:click="closeNav"/>
   <div class="footer" v-on:click="closeNav">
      <div class="contact">
        <div class="contact_content">
          <div class="left">
            <div class="contact_title">與我們聯絡</div>
            <div class="contact_subtitle">Contact Us</div>
            <img src="./../assets/line.png">
          </div>
          <div class="right" >
            <div v-for="item in data" :key="item" class="column">
              <span>
                <img v-bind:src="require('./../assets/img/' + item.picture + '.svg')" />
              </span>
              <span class="content">{{item.content}}</span>
            </div>
          </div>
        </div>
      </div>
      <div class="privacy"> © 2022 青松健康事業. All Rights Reserved.</div>
    </div>
</template>
<script>
import dataset from './../assets/data.json'
const data = dataset.jiasong
export default {
  name: 'mainpage',
  data () {
    return {
      data: data,
      sidebarOpen: false
    }
  },
  methods: {
    openNav: function () {
      this.sidebarOpen = true
    },
    closeNav: function () {
      this.sidebarOpen = false
    }
  },
  props: {
    msg: String
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}
#nav a {
  font-weight: bold;
  color: #2c3e50;
}
#nav a.router-link-exact-active {
  color: #42b983;
}
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #cae9be;
}
.navbar .picture {
  margin: 22px 6%;
}
.navbar .links{
  display: flex;
  column-gap: 24px;
  font-size: 24px;
  line-height: 28px;
  color: #2C2C2C;
  margin-right: 32px;
}
.navbar .links .link{
  color: #2C2C2C;
  font-weight: 600;
  text-decoration: none;
}
.sidenav {
  display: flex;
  flex-direction: column;
  row-gap: 24px;
  height: 100%; /* 100% Full-height */
  width: 250px;
  position: fixed; /* Stay in place */
  z-index: 1; /* Stay on top */
  top: 0; /* Stay at the top */
  right: 0;
  background-color: rgba(43, 50, 40, 0.8);
  overflow-x: hidden; /* Disable horizontal scroll */
  padding-top: 32px;
  transition: 0.5s;
}
.sidenav .link {
  text-decoration: none;
  color: #eee;
  /* padding-bottom: 10px; */
  /* border-bottom: solid 1px #eee; */
  /* font-weight: 600; */
  font-size: 20px;
}
.sidenav .close{
  display: flex;
  justify-content: flex-end;
  padding-right: 42px;
}
.footer .contact {
  background-color: #CAE9BE;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px 0;
}
.footer .contact .contact_content {
  display: flex;
  align-items: center;
}
.footer .left {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  row-gap: 12px;
  border-right: 4px solid #578369;
  padding-right: 24px;
  margin-right: 24px;
}
.footer .contact .left .contact_subtitle {
  font-weight: bold;
  font-size: 18px;
  line-height: 21px;
  color: #805800;
}
.footer .contact .left .contact_title {
  font-weight: bold;
  font-size: 24px;
  line-height: 28px;
  color: #29471C;
}
.footer .right {
  display: flex;
  flex-direction: column;
  row-gap: 12px;
}
.footer .right .column{
  display: flex;
  column-gap: 12px;
  align-items: center;
  justify-content: flex-start;
}
.footer .right .column .content{
  color: #29471C;
  font-size: 12px;
  line-height: 14px;
  font-weight: bold;
}
.footer .privacy {
  background-color: #578369;
  font-size: 12px;
  line-height: 14px;
  text-align: center;
  color: #ffffff;
  padding: 8px 0;
}
.links_md{
  display: none;
  position: absolute;
  right: 20px;
  top: 24px;
}
@media screen and (max-width: 1440px) {
  .navbar .picture{
    width: 60%;
  }
}
@media screen and (max-width: 1024px) {
  .navbar .links{
    display: none;
  }
  .links_md{
    display: block;
  }
  .footer .left {
    border-right: 2px solid #578369;
    padding-right: 12px;
    margin-right: 12px;
  }
  .footer .right .column {
    column-gap: 4px;
  }
}
</style>
