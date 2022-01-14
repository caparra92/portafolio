<template>
  <div class="footer">
    <p v-text="content" class="mx-auto"></p>
    <div class="flex justify-center items-center w-full mx-auto pt-3">
      <a class="mt-3" href="http://www.facebook.com/galoAbolicao">
        <img class="w-10 mr-3 mx-auto mt-5 pt-5" :src="require('../assets/facebook.svg')" alt="facebook" />
      </a>
      <a class="mt-3" href="http://www.github.com/caparra92">
        <img class="w-10 mr-3 mx-auto mt-5 pt-5" :src="require('../assets/github.svg')" alt="github" />
      </a>
      <a class="mt-3" href="http://www.linkedin.com/in/parra-camilo">
        <img class="w-10 mr-3 mx-auto mt-5 pt-5" :src="require('../assets/linkedin.svg')" alt="linkedin" />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Footer',
  props: {
    content: {
      type: String,
      default: 'Copyright ©2022 Camilo Parra'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.footer {
  padding-bottom: 10px;
  background: var(--secondary);
  width: 100%;
  height: 6em;
  color: var(--primary);
}

.footer p {
  width: 100%;
  margin: 0 auto;
  margin-top: 1em;
  padding: 0;
  position: absolute;
  align-items: center;
  text-align: center;
  color: var(--text-title);
}

@media all and (min-width: 320px) and (max-width: 768px) {
  .footer p {
    width: 100%;
    margin: 0;
    margin-top: 1.8em;
    padding: 0;
    position: absolute;
    align-items: center;
    text-align: center;
    left: 0;
  }
}
</style>
