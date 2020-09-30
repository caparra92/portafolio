<template>
  <section class="skills" id="skills">
    <h1 class="title">Skills</h1>
    <p>What would you like for your next project? These are some awesome tecnologies for your website or information system</p>
    <div class="flex justify-center content-center">
      <div class="arrow arrow-left"><button @click="slideLeft"><span>&#60;</span></button></div>
      <div class="w-2/3 h-auto lg:overflow-hidden overflow-x-scroll overflow-y-hidden pt-2 pb-2">
        <ul class="list-items" ref="slider">
          <li>
            <Card image="laravel.png" title="Laravel" description="Laravel PHP framework" ref="card1"></Card>
          </li>
          <li>
            <Card
              class="card"
              image="javascript.png"
              title="Javascript"
              description="The language of the web"
              ref="card2"
            ></Card>
          </li>
          <li>
            <Card
              class="card"
              image="java.png"
              title="Java"
              description="Web and native apps"
              ref="card3"
              :addTop="true"
              >
            </Card>
          </li>
          <li>
            <Card
              class="card"
              image="logo.png"
              title="Vue JS"
              description="Frontend javascript library"
              ref="card4"
            ></Card>
          </li>
          <li>
            <Card
              class="card"
              image="jquery.png"
              title="Jquery"
              description="Quickly and easy web interactions"
              ref="card5"
              :addTop="true"
            ></Card>
          </li>
          <li>
            <Card
              class="card"
              image="npm.png"
              title="NPM"
              description="Package manager for nodejs"
              ref="card6"
              :addTop="true"
              >
            </Card>
          </li>
          <li>
            <Card
              class="card"
              image="github.png"
              title="GitHub"
              description="Version control system"
              ref="card7"
              >
            </Card>
          </li>
          <li>
            <Card
              class="card"
              image="mysql.svg"
              title="MySql"
              description="Relacional database manager"
              ref="card8"
            ></Card>
          </li>
          <li>
            <Card
              class="card"
              image="ajax.png"
              title="Ajax"
              description="Asyncronous javascript and XML"
              ref="card9"
              :addTop="true"
            ></Card>
          </li>
          <li>
            <Card
              class="card"
              image="php.png"
              title="PHP"
              description="Program language for the server side"
              ref="card10"
              :addTop="true"
            ></Card>
          </li>
          <li>
            <Card
              class="card"
              image="css.svg"
              title="Css3"
              description="Styles for the real life pages"
              ref="card11"
            ></Card>
          </li>
          <li>
            <Card
              class="card"
              image="html.png"
              title="HTML 5"
              description="Markup language of the web"
              ref="card12"
            ></Card>
          </li>
          <li>
            <Card
              class="card"
              image="vscode.png"
              title="Visual Studio code"
              description="Intuitive text editor"
              ref="card13"
            ></Card>
          </li>
          <li>
            <Card
              class="card"
              image="wordpress.png"
              title="Wordpress"
              description="Top CMS system for blogs and websites"
              ref="card13"
            ></Card>
          </li>
        </ul>
      </div>
      <div class="arrow arrow-right"><button @click="slideRight"><span>&#62;</span></button></div>
    </div>
    <slot></slot>
  </section>
</template>

<script>
import Card from './card.vue'

export default {
  name: 'Skills',
  components: {
    Card
  },
  props: {
  },
  methods: {
    /* move (elem, start, end, step, callback) {
      const newStart = start - step
      if (newStart >= end) {
        elem.style.marginLeft = newStart + '%'
        setTimeout(() => this.move(elem, newStart, end, step, callback), 7)
      } else {
        callback()
      }
    }, */
    slideLeft () {
      const slider = this.$refs.slider
      slider.classList.remove('list-items')
      slider.className = 'move-slider'
      slider.style.transform += 'translateX(-9%)'
    },
    slideRight () {
      const slider = this.$refs.slider
      slider.classList.remove('list-items')
      slider.className = 'move-slider'
      slider.style.transform += 'translateX(9%)'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.skills {
  margin: 0 auto;
  height: 100vh;
}
.card {
  width: 10em;
  height: 20em;
}

p {
  margin: 0 auto;
  padding: 0;
  max-width: 80%;
}

.here {
  color: black;
  font-size: 1em;
  transition: all 0.25s;
  -webkit-transition: all 0.25s;
  -moz-transition: all 0.25s;
}

.here:hover {
  font-size: 1.3em;
}

.btn {
  position: absolute;
  font-size: 0.5em;
  border-radius: 5px;
  color: black;
  cursor: pointer;
  border: none;
  background: transparent;
}
.slider {
  width: 75%;
  margin: 1em auto;
  padding-bottom: .3em;
  overflow: hidden;
}

.arrow {
  width: 30px;
}

.arrow button {
  outline: none;
  font-size: 3em;
  color: #413968
}

.arrow-left {
  margin: auto;
  margin-right: 2em;
}

.arrow-right {
  margin: auto;
  margin-left: 2em;
}

.list-items {
  display: flex;
  width: 300%;
  padding: 0;
  animation: slider 20s infinite alternate cubic-bezier(0.17, 0.67, 0.83, 0.67);
}

.move-slider {
  display: flex;
  width: 300%;
  padding: 0;
  transition: all 0.5s cubic-bezier(0.075, 0.82, 0.165, 1);
}

.list-items:hover {
  cursor: pointer;
  animation-play-state: paused;
}

.list-items li {
  width: auto;
}

.add-space {
  position: relative;
  padding-top: 3em;
  margin: 2em 0;
  top: 50%;
}

@keyframes slide-left {
  0% {
    margin-left: 0;
  }
  50% {
    margin-left: -50%;
  }
  100% {
    margin-left: -100%;
  }
}

@keyframes slider {
  0% {
    margin-left: 0;
  }
  20% {
    margin-left: 0;
  }

  25% {
    margin-left: -100%;
  }
  45% {
    margin-left: -100%;
  }

  50% {
    margin-left: -200%;
  }
  70% {
    margin-left: -200%;
  }

  75% {
    margin-left: -200%;
  }
  100% {
    margin-left: -200%;
  }
}

@media all and (min-width: 320px) and (max-width: 768px){
  .skills {
  margin: 0 auto;
  height: 100vh;
  }

  p {
    margin-bottom: 1.5em;
  }

  .here {
    color: black;
    font-size: 1em;
    transition: all 0.25s;
    -webkit-transition: all 0.25s;
    -moz-transition: all 0.25s;
  }

.here:hover {
  font-size: 1.3em;
}

.btn {
  position: absolute;
  font-size: 0.5em;
  border-radius: 5px;
  color: black;
  cursor: pointer;
  border: none;
  background: transparent;
}
.slider {
  width: 75%;
  margin: auto;
  padding-bottom: .3em;
  overflow: hidden;
}

.list-items {
  display: flex;
  width: 300%;
  padding: .2em 0;
  animation: none;
}

.list-items:hover {
  cursor: pointer;
  animation-play-state: paused;
}

.list-items li {
  width: auto;
}

.add-space {
  position: relative;
  padding-top: 3em;
  margin: 2em 0;
  top: 50%;
}
}
</style>
