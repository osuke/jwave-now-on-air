<template>
  <div class="item">
    <div class="artwork"><img :src="item.img" v-if="item.img.length > 0" /></div>
    <div class="info">
      <div>曲名: <span>{{ item.title }}</span></div>
      <div>アーティスト名: <span>{{ item.artist }}</span></div>
      <div>番組名: {{ item.program_title }}</div>
      <div><a :href="item.youtube" target="_blank">YouTube</a></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Song',
  props: ['item']
}
</script>

<style scoped>
.item {
  display: flex;
  margin-bottom: 12px;
}
.artwork {
  width: 100px;
  height: 100px;
}
.artwork:empty {
  background: #f0f0f0;
}
.artwork img {
  width: 100%;
  height: auto;
}
.info {
  padding-left: 12px;
  flex: 1;
}
.info span {
  font-weight: bold;
}
</style>
