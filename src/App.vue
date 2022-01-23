<template>
  <div id='app'>
    <Sidebar @onTranslate = translateLeft @onReturn = returnLeft />
    <div ref="mainContent">
      <Header />
      <Section />
      <Projects />
      <Skills>
      </Skills>
      <Contact>
        <p>
          You can contact me for email through <b>caparra92@gmail.com</b> or in the social media section below the menu
        </p>
        <p slot="textLine">You can call me on +57 3214719068 if you want to get in touch more quickly.
          (The country code is not necessary if you live in Colombia)
        </p>
      </Contact>
      <Footer />
    </div>
  </div>
</template>

<script>
import Sidebar from './components/sidebar.vue'
import Header from './components/header.vue'
import Section from './components/section.vue'
import Projects from './components/projects.vue'
import Skills from './components/skills.vue'
import Contact from './components/contact.vue'
import Footer from './components/footer.vue'

export default {
  name: 'App',
  components: {
    Sidebar,
    Header,
    Section,
    Projects,
    Skills,
    Contact,
    Footer
  },
  data () {
    return {
      mainContent: 'main-content'
      // pdfLink: require('./assets/resume.pdf')
    }
  },
  props: {},
  methods: {
    translateLeft () {
      this.$refs.mainContent.className = 'main-content'
    },
    returnLeft () {
      this.$refs.mainContent.className = 'main'
    }
  }
}
</script>

<style>
@import url('https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css');
@import url('https://fonts.googleapis.com/css?family=Josefin+Sans&display=swap');

:root {
  --primary: #f3f5f9;
  --secondary: #462d6d;
  --text-title: #2c2c2c;
  --border: #5c5c5c;
  --btn-primary: #62468f;
  --black: #000;
  --white: #fff;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  text-decoration: none;
  list-style: none;
  transition: all .5s ease-in-out;
}
html {
  scroll-behavior: smooth;
}
body {
  background: var(--primary);
  text-align: center;
  font: 300 20px/1.7 'Josefin Sans';
  overflow-x: hidden;
}
figure {
  padding: 10px;
}

p {
  text-align: justify;
  font-size: 1em;
  line-height: 1.5em;
}
a {
  color: var(--secondary);
}
.main-content {
  margin-left: 20%;
  transition: all 0.25s;
  -webkit-transition: all 0.25s;
}
.main {
  margin: 0;
  padding: 0;
  transition: all 0.25s;
  -webkit-transition: all 0.25s;
  -moz-transition: all 0.25s;
}
.container {
  position: relative;
  padding-top: 130px;
  margin-bottom: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.title {
  margin: 0 auto;
  margin-bottom: 40px;
  font-size: 60px;
  text-transform: uppercase;
  text-align: center;
  width: 100%;
  color: var(--text-title);
}
.line {
  margin-bottom: 1em;
}

.btn-custom {
  position: relative;
  display: inline;
  top: 2em;
  color: var(--btn-primary);
  padding: 0.5em;
  margin: 0.5em;
  background: var(--secondary);
  border: 1px solid var(--border);
  border-radius: 5px;
}

.btn-custom .fa {
  padding: 0.2em;
}

.btn-custom:hover {
  background: var(--secondary);
}

#app {
  font-family: 'Josefin Sans' sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

/* Slider */
.slider {
  width: 75%;
  margin: 1em auto;
  padding-bottom: .3em;
  overflow: hidden;
}

.slider-container {
  width: 100%;
  overflow-x: scroll;
  overflow-y: hidden;
}

.card-list {
  display: flex;
  align-items: center;
  justify-content: center;
  max-width: 80%;
  margin-top: 20px;
}

.card {
  width: 10em;
  height: 20em;
}

.arrow {
  width: 30px;
}

.arrow button {
  outline: none;
  font-size: 3em;
  color: var(--text-title)
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

@media screen and (min-width: 320px) and (max-width: 768px) {
  .main-content {
    margin: 0;
  }

  p {
    font-size: 0.8em;
    margin: 0 1.5em;
  }

  .title {
    margin-bottom: 30px;
  }

  /* Slider */
  .skills {
  margin: 0 auto;
  height: 100vh;
  }

  p {
    margin-bottom: 1.5em;
    color: var(--text-title);
  }

  .here {
    font-size: 1em;
    transition: all 0.25s;
    -webkit-transition: all 0.25s;
    -moz-transition: all 0.25s;
  }

  .here:hover {
    font-size: 1.3em;
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
