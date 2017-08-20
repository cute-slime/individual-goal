<template>
  <div class="feed_list">
    <div v-for="item in items">
      {{item.description}}
    </div>
  </div>
</template>

<script>
  export default {
    name: 'FeedList',
    components: {},
    data () {
      return {
        apiEndpoint: 'http://localhost:8081/',
        version: 'v1.0',
        api: 'feed',
        items: [{description: 'test'}, {description: 'is'}, {description: 'wandaful'}]
      }
    },
    mounted: function () {
      this.fetchData()
    },
    watch: {
      $route: 'fetchData'
    },
    methods: {
      fetchData () {
        console.log('요기서 fetch api data!')
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
