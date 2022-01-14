<template>
  <div class="footer">
    <p v-text="content" class="mx-auto"></p>
    <div class="footer-social">
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
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  padding-bottom: 10px;
  background: var(--primary);
  width: 100%;
  height: auto;
  color: var(--primary);
}

.footer p {
  width: 100%;
  margin-top: 1em;
  padding: 0;
  align-items: center;
  text-align: center;
  color: var(--text-title);
}

.footer .footer-social {
  display: flex;
  justify-content: center;
  align-items: center;
}

.footer .footer-social a {
  display: inline-block;
  margin-bottom: 1em;
  padding-bottom: 1em;
}

@media all and (min-width: 320px) and (max-width: 768px) {
  .footer p {
    width: 100%;
    margin: 0;
    margin-top: 1.8em;
    padding: 0;
    left: 0;
  }

  .footer .footer-social a {
    margin: .5em;
    padding-bottom: .5em;
  }
}
</style>
