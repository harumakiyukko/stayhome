<template>
  <div id="app">
    <div class="links">
      <h1><img alt="stayhome" src="./assets/art/0404.png" class="on Twitter"><p><span>みんなの</span>#stayhome</p></h1>
      <div>
        <a class="snsbtn" href="https://twitter.com/search?q=%23stayhome&src=typed_query"><img alt="logo" src="./assets/twitter.png" class="on Twitter"></a>
        <a class="snsbtn size2"  href="https://www.youtube.com/results?search_query=%23stayhome"><img alt="logo" src="./assets/youtube.png" class="on YouTube"></a>
        <a class="snsbtn size2"  href="https://vimeo.com/search?q=stayhome"><img alt="logo" src="./assets/vimeo.png" class="on vimeo"></a>
        <a class="snsbtn"  href="https://www.instagram.com/explore/tags/stayhome/"><img alt="logo" src="./assets/instagram.png" class="on Instagram"></a>
        <a class="snsbtn size3" href="https://www.pinterest.jp/search/pins/?q=stayhome"><img alt="logo" src="./assets/pinterest.svg" class="on Pinterest"></a>
      </div>
    </div>

    <h1><img alt="stayhome" src="./assets/art/0403.png" class="on Twitter"><p><span>著名人の</span>#stayhome</p></h1>
    <Posts msg="Welcome to stayhome.fmw-harumaki.jp"/>


    <div class="logobox">
      <img alt="logo" src="./assets/art/0331.png" class="logo">
      <div class="logotext">
        <h2>#stayhome のために、癒しになるようなSNS投稿を集めています。</h2>
        <p>偏りなく集めていきたいと思いますが、気づいたことがあれば<a href="https://twitter.com/harumakiyukko">twitter</a>までご連絡下さい。<br>
          共同編集は<a href="https://github.com/harumakiyukko/stayhome">github</a>と
          <a href="https://docs.google.com/spreadsheets/d/1_k__CMAdsbh_Ghc2s2bwbN-IKKTQq8FlAexaLLCIa2Q/edit?usp=sharing">googleスプレッドシート</a>
          でやっています。<br>
          一緒に取り組んでくださる方はぜひご連絡ください。</p>
        <p>
          thank you all !<br>
          art work : <a href="https://twitter.com/Hashi_ko845">@Hashi_ko845</a><br>
          preloader : <a href="https://dribbble.com/shots/1379948-Morph-Shape-Preloader-GIF">dribbble by Mantas Bačiuška</a><br>
          vue-youtube-embed : <a href="https://github.com/kaorun343/vue-youtube-embed">@kaorun343</a><br>
          vue-tweet-embed : <a href="https://github.com/tonickkozlov/vue-tweet-embed">@tonickkozlov</a><br>
          and Vue and npm and yarn and you!
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import Posts from './components/Posts.vue'

export default {
  name: 'App',
  components: {
    Posts
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Courgette&display=swap');
body {
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #282827;
  background: #f6f5ea;
  margin: 0;
}
.logobox {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 80px 0;
}
.logo{
  width: 60%;
  max-width: 300px;
  margin-right: 20px;
}
.logotext {
  text-align: left;
}
@media (max-width: 680px) {
  .logobox {
    display: block;
    padding: 80px 30px;
  }
}
h2 {
  font-size: 1rem;
}
h1 {
  margin: 0;
  padding: 60px 0;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Courgette', cursive;
  flex-wrap: wrap;
  text-shadow: 1px 1px 1px yellow;
}
h1 img {
  width: 160px;
  margin: 0;
}
h1 span {
  font-size: 1.2rem;
  line-height: 1.6rem;
  display: block;
}
h1 p {
  position: relative;
  left: -.5rem;
}
.snsbtn {
  margin: 0 20px;
}
.snsbtn img {
  height: 60px;
}
.snsbtn.size2 img {
  height: 30px;
  margin: 15px 0;
}
.snsbtn.size3 img {
  height: 40px;
  margin: 10px 0;
}
</style>
