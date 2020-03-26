<template>
    <div class="footer">
        <p v-text="content"></p>
    </div>
</template>

<script>
export default {
  name: 'Footer',
  props: {
    content: {
      type: String,
      default: 'Copyright ©2020 Camilo Parra'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
