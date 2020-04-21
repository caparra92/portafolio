<template>
  <section class="container project" id="project">
    <h1 class="title">Projects</h1>
    <p v-text="p1"></p>
    <p class="textImg" v-text="gitHub"></p>
    <figure>
        <a href="https://github.com/caparra92" target="blank" >
          <img :src="require('../assets/github.png')" alt="Github" width="80px" height="80px" class="git" />
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
  margin: 0 auto;
  height: 100vh;
}

.project p {
  position: relative;
  max-width: 850px;
  text-align: justify;
  left: 20%;
}

.git {
  position: relative;
  margin-left: 15px;
  margin-top: 50px;
  left: 65px;
  bottom: 140px;
  transition: all 0.25s;
  -webkit-transition: all 0.25s;
  -moz-transition: all 0.25s;
}

.git:hover {
  width: 100px;
  height: 100px;
  border: none;
}

.textImg {
  margin-right: 200px;
}

@media only screen and (min-width: 320px) and (max-width: 736px){
  .project {
    margin: 0 auto;
    height: 100vh;
  }

  .project p {
    position: relative;
    max-width: 23em;
    text-align: justify;
    left: 10%;
    padding-right: 3.3em;
  }

  .git {
    display: none;
  }

  .textImg {
    position: relative;
    max-width: 23em;
    text-align: justify;
    left: 10%;
    padding-right: 3.3em;
    margin-right: 0;
  }
}
</style>
