<template>
  <div id="app">
    <header id="layHeader">
      <div class="lay-top">
        <div class="lay-top-pad">
          <div class="lay-top-left">
            <img src="/imgs/icons/Logo2.png" alt="Alternate Text" />

            <span>朝夕集市网1</span>
          </div>
          <div class="lay-top-right">
            <span>注册</span>
            <span>登录</span>
          </div>
        </div>
      </div>
      <div class="lay-nav">
        <div class="lay-nav-pad">
          <ul>
            <li>
              <a href="/Home/Home">首页</a>
            </li>
            <li v-for="nav in navs" :key="nav.id">
              <a href="#">{{nav.typeName}}</a>
            </li>
          </ul>
        </div>
      </div>
      <div class="lay-back-title">
        <img src="/imgs/icons/轮播-3-全栈.jpg" />
      </div>
    </header>
    <div class="lay-body"></div>这是页面头
    这是页面尾
  </div>
</template>
<script>
export default {
   data() { return {navs:[]} },
        mounted() {
            this.getNavs();
        },
        methods: {
            getNavs() {
                var that = this;
                $.get("/Home/GetNavs", {}, function (res) {
                    that.navs = res;
                });

            },
        }
}
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body,
ul,
li {
  margin: 0px;
  padding: 0px;
}

* {
  padding: 0px;
  margin: 0px;
}

header .lay-top {
  width: 100%;
  background-color: #f0f0f0;
}

header .lay-top-pad {
  height: 40px;
  width: 1200px;
  margin-left: auto;
}

header .lay-top .lay-top-left {
  float: left;
  height: 40px;
  line-height: 40px;
}

header .lay-top .lay-top-left img {
  width: 32px;
  vertical-align: middle;
}

header .lay-top .lay-top-left span {
  font-size: 15px;
}

header .lay-top .lay-top-right {
  float: right;
  height: 40px;
  line-height: 40px;
}

header .lay-top .lay-top-right span {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
  font-size: 13px;
}

header .lay-nav {
  background-color: #134398;
}

header .lay-nav.lay-nav-pad {
  height: 40px;
  line-height: 40px;
  width: 1200px;
  margin: auto;
}

header .lay-nav .lay-nav-pad ul {
  height: 40px;
}

header .lay-nav .lay-nav-pad ul li {
  float: left;
  list-style: none;
  padding-left: 30px;
  padding-right: 30px;
  line-height: 26px;
  border-left: 1px solid #ccc;
  height: 26px;
  margin-top: 7px;
  font-size: 13px;
}

header .lay-nav .lay-nav-pad ul li:first-child {
  padding-left: 150px;
  border-left: 0 none;
}

header .lay-nav .lay-nav-pad ul li a {
  color: #fff;
  text-decoration: none;
}

header .lay-nav .lay-nav-pad ul li a:visited {
  color: #fff;
}

.lay-back-title {
  height: 136px;
  text-align: center;
  background-color: #001125;
}

.lay-back-title img {
  height: 136px;
  width: 100%;
}
</style>
