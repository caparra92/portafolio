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
.footer {
  background: #fff;
  width: 100%;
  height: 5em;
}

.footer p {
  margin-top: 2em;
  padding: 0;
  position: absolute;
  align-items: center;
  text-align: center;
  left: 45%;
}
</style>
