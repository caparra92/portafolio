<template>
  <section class="container project" id="project">
    <h1 class="title">Projects</h1>
    <p v-text="p1"></p>
    <p class="textImg" v-text="gitHub"></p>
    <figure>
        <a href="https://github.com/caparra92" target="blank" >
          <img :src="require('../assets/github.png')" alt="Github" width="100px" height="100px" class="git" />
        </a>
    </figure>
  </section>
</template>

<script>
export default {
  name: 'Projects',
  props: {
    p1: {
      type: String,
      default: "Some personal and client projects you can review and test what of these dou you like more?. Remind that i'm updating this section frecuently, Therefore you will be update in all my lastest jobs."
    },
    gitHub: {
      type: String,
      default: 'Check my GitHub profile for contributions and tips, i really like to learn of other expertise developers and clients, thanks for your help!'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.project {
  max-width: 1055px;
  margin: 0 auto;
  height: 100vh;
}

.git {
  position: relative;
  margin-left: 55px;
  left: 65px;
  bottom: 140px;
  transition: all 0.25s;
  -webkit-transition: all 0.25s;
  -moz-transition: all 0.25s;
}

.git:hover {
  width: 130px;
  height: 130px;
  border: none;
}

.textImg {
  width: 50%;
  position: relative;
  left: 40px;
  top: 10px;
}
</style>
