<template>
  <section class="container project" id="project">
    <h1 class="title">Projects</h1>
    <p v-text="p1"></p>
    <p class="git">Check my <a href="https://github.com/caparra92" target="blank" >GitHub </a>profile for contributions and tips, i really like to learn of other expertise developers and clients, thanks for your help!</p>
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
      default: ''
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
  margin: 0 auto;
  position: relative;
  max-width: 80%;
  text-align: justify;
  margin-bottom: 15px;
}

.git a {
  color: black;
  transition: all 0.25s;
  -webkit-transition: all 0.25s;
  -moz-transition: all 0.25s;
}

.git a:hover {
  color: #6b6969;
}

@media only screen and (min-width: 320px) and (max-width: 768px){
  .project {
    margin: 0 auto;
    height: 100vh;
  }

  .project p {
    text-align: justify;
  }

  .git {
    display: none;
  }

  .textImg {
    text-align: justify;
    margin-right: 24px;
  }
}
</style>
