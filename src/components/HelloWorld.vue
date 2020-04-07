<template>
  <div>
    <div v-if="isFetching" class="loading"><img src="../assets/preloader.gif"></div>
    <div class="allbox">
      <div class="item" v-for="(ss, index) in sources" :key="index">
        <youtube v-if="ss.from == 'youtube'" :video-id="ss.id" class="youtubebox" player-width="100%" player-height="100%"></youtube>
        <Tweet v-if="ss.from == 'twitter'" :id="ss.id" class="twitterbox"><div class="spinner"></div></Tweet>
      </div>
    </div>
  </div>
</template>

<script>
    import { Tweet } from 'vue-tweet-embed'
    import axios from 'axios'


export default {
  name: 'HelloWorld',
    data() {
        return {
            sources : [],
            isFetching : true,
        }
    },
    components: {
      Tweet
    },
    mounted: function () {
        this.getSources()
    },
    methods: {
      getSources: function () {
          axios.get(`https://script.googleusercontent.com/macros/echo?user_content_key=wbhREdoco-BwUjuDF4fnCbqUD3fO_T7CABOuKOfNpUKWhVoKq48m7VfeMKD6SK2kVZwy37d8H6YVt4-wQcvO5jx7MJuLdJK2m5_BxDlH2jW0nuo2oDemN9CCS2h10ox_1xSncGQajx_ryfhECjZEnLYAU3DiAHu-kijvB0iw7VMPtjNjxkBdtCKuHaI9BvaQl8PymMaPVAyhRYnzsJfjjOQAcA3IDdi1&lib=MkHnTebKaGAHmnjCG0nw6NybqL8bBmoa-`)
              .then(({ data }) => {
              this.sources = data
      })
          .catch((error) => {
              this.data = []
          throw error
      })
          .finally(() => {
              this.isFetching = false
      })
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.youtubebox {
  border: solid 1px #FFF;
  background: #FFF;
  padding: 10px;
  border-radius: 1%;
  margin: 0 10px 10px;
  width: 300px;
  height: 200px;
  -webkit-column-break-inside: avoid;
  page-break-inside: avoid;
  break-inside: avoid;
}
.twitterbox {
  margin: 0 10px 10px;
  width: 320px;
  -webkit-column-break-inside: avoid;
  page-break-inside: avoid;
  break-inside: avoid;
}
.allbox {
  width: 90%;
  max-width: 1380px;
  margin: auto;
  column-count: 4;
  column-gap: 0;
}
@media (max-width: 900px) {
  .allbox {
    width: 680px;
    margin: auto;
    column-count: 2;
  }
}

@media (max-width: 680px) {
  .allbox {
    width: 340px;
    margin: auto;
    column-count: 1;
  }
}
.loading {
  margin: auto;
  text-align: center;
}
</style>
