<template>
  <section class="container project" id="project">
    <h1 class="title">Projects</h1>
    <p v-text="p1"></p>
    <p class="git">Check my <a href="https://github.com/caparra92" target="blank" >GitHub </a>profile for contributions and tips, i really like to learn of other expertise developers and clients, thanks for your help!</p>
    <div class="card-list">
      <div class="arrow arrow-left"><button @click="slideLeft"><span>&#60;</span></button></div>
      <div class="slider-container">
        <ul class="list-items" ref="slider">
          <li>
            <a href="http://basic-card-component.netlify.app" target="_blank">
              <Card
                class="card col-sm-12 text-gray-900"
                image="card.png"
                title="component.netlifly.app"
                description="Simple card component made with css flexbox"
                ref="card13"
              ></Card>
            </a>
          </li>
          <li>
            <a href="https://caparra.netlify.app" target="_blank">
              <Card
                class="card col-sm-12 text-gray-900"
                image="portafolio.png"
                title="caparra.netlify.app"
                description="This portafolio made with vuejs and tailwind css"
                ref="card13"
              ></Card>
            </a>
          </li>
          <li>
            <a href="https://eventspage.netlify.app" target="_blank">
              <Card
                class="card col-sm-12 text-gray-900"
                image="events.png"
                title="eventspage.netlify.app"
                description="Events page mockup made with HTML and CSS"
                ref="card13"
              ></Card>
            </a>
          </li>
          <li>
            <a href="https://appmoda.netlify.app" target="_blank">
              <Card
                class="card col-sm-12 text-gray-900"
                image="appmoda.png"
                title="appmoda.netlify.app"
                description="Eccommerce made with vuejs and vuetify framework"
                ref="card13"
              ></Card>
            </a>
          </li>
        </ul>
      </div>
      <div class="arrow arrow-right"><button @click="slideRight"><span>&#62;</span></button></div>
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
  },
  methods: {
    slideLeft () {
      const slider = this.$refs.slider
      const ArrayItems = [...slider.children]
      slider.classList.remove('list-items')
      slider.className = 'move-slider'
      slider.style.transform += `translateX(-${ArrayItems[0].clientWidth}px)`
    },
    slideRight () {
      const slider = this.$refs.slider
      const ArrayItems = [...slider.children]
      slider.classList.remove('list-items')
      slider.className = 'move-slider'
      slider.style.transform += `translateX(${ArrayItems[0].clientWidth}px)`
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.project {
  height: 100vh;
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
  color: var(--text-title);
}

.git a {
  color: var(--text-title);
  transition: all 0.25s;
  -webkit-transition: all 0.25s;
  -moz-transition: all 0.25s;
}

.git a:hover {
  color: #6b6969;
}

@media all and (min-width: 320px) and (max-width: 768px){
  .project {
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
