<template>
  <div @click="fetchData" class="btn">更新する</div>
</template>

<script>
export default {
  name: 'FetchBtn',
  methods: {
    fetchData: function () {
      this.$emit('fetch')
    }
  }
}
</script>

<style scoped>
.btn {
  padding: 12px;
  text-align: center;
  margin-bottom: 24px;
}
</style>
