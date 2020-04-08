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
        <a class="snsbtn size3" href="https://www.tiktok.com/tag/%E5%AE%B6%E3%81%AB%E3%81%84%E3%82%8B%E3%81%A0%E3%81%91%E3%81%A7%E4%B8%96%E7%95%8C%E3%81%AF%E6%95%91%E3%81%88%E3%82%8B?lang=ja"><img alt="logo" src="./assets/tiktok.svg" class="on tiktok"></a>
        <a class="snsbtn size3" href="https://www.google.com/doodles/stay-home-save-lives"><img alt="logo" src="./assets/google.svg" class="on google"></a>
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

    <transition>
      <div v-show="scY > 300" @click="toTop" class="btn_back_box">
        <img src="./assets/arrow.svg" class="btn_back" @click="toTop" >
      </div>
    </transition>
  </div>
</template>

<script>
import Posts from './components/Posts.vue'

export default {
  name: 'App',
  components: {
    Posts
  },
    data() {
        return {
            scTimer: 0,
            scY: 0,
        }
    },
    mounted: function () {
        window.addEventListener("scroll", this.scEvent)
    },
    destroyed: function () {
        window.addEventListener("scroll", this.scEvent)
    },
    methods: {
        toTop() {
            var scrolled = window.pageYOffset;
            window.scrollTo(0, Math.floor(scrolled * 0.8));
            if (scrolled > 0) {
                window.setTimeout(this.toTop, 10);
            }
        },
        scEvent() {
            if (this.scTimer) return;
            this.scTimer = setTimeout(() => {

                this.scY = window.scrollY;

            clearTimeout(this.scTimer);
            this.scTimer = 0;

        }, 100);
        }
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
  text-shadow: 1px 1px 1px #f4ecde;
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
  .btn_back_box {
    position: fixed;
    bottom: 7vh;
    right: 5%;
    width: 80px;
    height: 80px;
    z-index: 10000;
    transition-duration: 0.2s;
    transition: all 0.6s;
  }
  .btn_back_box .btn_back {
    filter: drop-shadow(0px 1px 3px #f6f5ea);
  }
  .btn_back_box:hover {
     bottom: 8vh;
   }

  .btn_back_box.v-enter,
  .btn_back_box.v-leave-to {
     opacity: 0;
     bottom: 10px;
   }
  @media screen and (max-width: 680px) {
    .btn_back_box {
      position: relative;
      bottom: 60px;
      right: 0;
      width: 60px;
      height: 60px;
      margin: auto;
    }
  }
</style>
