<template>
  <section class="project" id="project">
    <h1 class="title">Projects</h1>
    <p v-text="p1"></p>
    <p class="git">Check my <a href="https://github.com/caparra92" target="blank" >GitHub </a>profile for contributions and tips, i really like to learn of other expertise developers and clients, thanks for your help!</p>
    <div class="project-list">
      <div class="row flex">
        <a href="http://deleite.domipan.co" target="_blank">
          <Card
            class="card col-sm-12 text-grey-900"
            image="deleite.png"
            title="deleite.domipan.co"
            description="Information system mades with Laravel and Ajax"
            ref="card13"
          ></Card>
        </a>
        <a href="https://parracamilo.tk" target="_blank">
          <Card
            class="card col-sm-12 text-grey-900"
            image="portafolio.png"
            title="parracamilo.tk"
            description="This portafolio mades with vuejs and tailwind css"
            ref="card13"
          ></Card>
        </a>
        <a href="https://appmoda.netlify.app" target="_blank">
          <Card
            class="card col-sm-12 text-grey-900"
            image="appmoda.png"
            title="appmoda.netlify.app"
            description="Eccommerce made with vuejs and vuetify framework"
            ref="card13"
          ></Card>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import Card from '@/components/card.vue'

export default {
  name: 'Projects',
  components: {
    Card
  },
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

.project-list {
  max-width: 80%;
  margin: 0 auto;
}
.card {
  width: 10em;
  height: 12em;
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

@media all and (min-width: 320px) and (max-width: 768px){
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
