<!-- bootstrap 
  1. bootstrap install
  2. main.js 
  import 'bootstrap'
  import 'bootstrap/dist/css/bootstrap.min.css'
  vue router
  1.npm install vue-router@4 설치
  2. main.js     .use(라우터만든거)
  3. <router-view></router-view> -->
<template>
  <nav class="navbar navbar-expand-lg bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Joobong</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Features</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Shop</a>
        </li>
        <li class="nav-item">
          <a class="nav-link disabled">Contact</a>
        </li>
      </ul>
    </div>
  </div>
</nav>
<!-- <div class="container mt-4">
  <h5>VUE 개발자의 블로그입니다.</h5>
  <p> VUE.js로 생성했습니다</p>
</div> -->

<!-- 다른 페이지 이동링크 -->
<router-link to="/" style="padding: 10px">홈페이지</router-link>
<router-link to="/list">리스트</router-link>


<div class="mt-4">
<router-view :블로그글 = '블로그글'></router-view>
</div>
<!--props :작명 = "데이터"-->
<!-- <List :블로그글 = "블로그글"/> -->

</template>

<script>
// import List from './components/List.vue';
import blog from './assets/blog.js';


export default {
  name: 'App',
  data(){
    return{
      블로그글 : blog
    }
  },

  components: {
  //  List : List,
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

</style>
