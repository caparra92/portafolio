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
          You can contact me for email through caparra92@gmail.com or in the social media section below the menu
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
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  text-decoration: none;
  list-style: none;
}
html {
  scroll-behavior: smooth;
}
body {
  background: #f3f5f9;
  text-align: center;
  font: 300 20px/1.7 'Josefin Sans';
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
  color: #fff;
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
}
.container {
  margin: 5px;
  margin-bottom: 20px;
}
.title {
  margin: 0 auto;
  margin-bottom: 40px;
  font-size: 60px;
  text-transform: uppercase;
  text-align: center;
  width: 100%;
}
.line {
  margin-bottom: 1em;
}

.btn-custom {
  position: relative;
  display: inline;
  top: 2em;
  color: #2c3e50;
  padding: 0.5em;
  margin: 0.5em;
  background: #fff;
  border: 1px solid rgb(92, 92, 92);
  border-radius: 5px;
}

.btn-custom .fa {
  padding: 0.2em;
}

.btn-custom:hover {
  background: #f3f5f9;
}

#app {
  font-family: 'Josefin Sans' sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
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
}
</style>
