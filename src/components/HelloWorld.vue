<template>
  <div class="allbox">
    <div class="item" v-for="(ss, index) in sources" :key="index">
      <youtube v-if="ss.from == 'youtube'" :video-id="ss.id" class="youtubebox" player-width="100%" player-height="100%"></youtube>
      <Tweet v-if="ss.from == 'twitter'" :id="ss.id" class="twitterbox"><div class="spinner"></div></Tweet>
    </div>
  </div>
</template>

<script>
    import { Tweet } from 'vue-tweet-embed'

export default {
  name: 'HelloWorld',
    data() {
        return {
            sources : [
                { from: 'youtube', id: 'mKmFLZhfDtE'},
                { from: 'twitter', id: '1247105206023680000'},
                { from: 'twitter', id: '1247117149287538688'},
                { from: 'twitter', id: '1247118159095541760'},
                { from: 'youtube', id: 'jSM0h8VPSZk'},
                { from: 'twitter', id: '1247011149758922753'},
                { from: 'youtube', id: '3OO5zq1PBIM'},
                { from: 'youtube', id: '8kqvXDLl6O0'},
                { from: 'youtube', id: 'ELhCZI8V2KQ'},
                { from: 'youtube', id: 'b4DeMn_TtF4'},
                { from: 'twitter', id: '1246967272075218944'},
                { from: 'twitter', id: '1247006212673032192'},
                { from: 'twitter', id: '1246047171134107648'},
            ]
        }
    },
    components: {
      Tweet
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
</style>
