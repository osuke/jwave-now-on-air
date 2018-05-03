<template>
  <div class="songList">
    <FetchBtn @fetch="fetchData">更新する</FetchBtn>
    <Song
      v-for="(item, key) in items"
      :item="item"
      :key="key"
    />
  </div>
</template>

<script>
import FetchBtn from './FetchBtn.vue'
import Song from './Song.vue'

export default {
  name: 'SongList',
  components: {
    FetchBtn,
    Song
  },
  data: function () {
    return {
      items: []
    }
  },
  methods: {
    fetchData: function () {
      const url = 'https://query.yahooapis.com/v1/public/yql?q=select%20*%20from%20xml%20where%20url%20%3D%20%27https%3A%2F%2Fradiko.jp%2Fv3%2Ffeed%2Fpc%2Fnoa%2FFMJ.xml%3Fv%3D' + new Date().getTime() + '%27&format=json&env=store%3A%2F%2Fdatatables.org%2Falltableswithkeys';
      fetch(url).then((res) => {
        return res.json();
      }).then((json) => {
        let items = json.query.results.feed.noa.item
        items.map((val) => {
          val.youtube = `https://www.youtube.com/results?search_query=${val.title} ${val.artist}`
        })
        this.items = items
      })
    }
  },
  created: function () {
    this.fetchData()
  }
}
</script>

<style scoped>
.songList {
  max-width: 600px;
  padding: 16px;
  margin: 0 auto;
  box-sizing: border-box;
}
</style>
