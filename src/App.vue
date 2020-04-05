<template>
  <div id='app'>
    <Sidebar @onTranslate = translateLeft @onReturn = returnLeft />
    <div ref="mainContent">
      <Header />
      <Section />
      <Projects />
      <Skills />
      <Contact />
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
  margin-bottom: 40px;
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
  margin-bottom: 40px;
  font-size: 60px;
  text-transform: uppercase;
}
#app {
  font-family: 'Josefin Sans' sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
