<template>
  <div>
    <i class="fa fa-ellipsis-v" v-on:click="aa"></i>
  </div>
</template>

<script>
  export default {
    name: 'PostOptionMenu',
    data () {
      return {}
    },
    methods: {
      aa () {
        this.$modal.show('dlg-post-option-menu', {})
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
