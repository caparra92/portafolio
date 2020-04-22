<template>
  <section class="container about" id="about">
    <h1 class="title">About</h1>
    <img :src="require('../assets/camilo.jpg')" alt="Camilo" width="400px" height="400px" />
    <h2>Camilo Parra, Web Developer</h2>
    <p>I was born in 1992 in Pasto city of Colombia, degree in computer science of the University of Nariño in 2017, he really likes work with web development specially with javascript and HTML tecnologies.</p>
    <p>I worked in diferents areas as teaching office packages and basic concepts of information technologies.</p>
    <p>I'm a teacher for profesion but developer for vocation.</p>
  </section>
</template>

<script>
export default {
  name: 'Section',
  props: {}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.about {
  width:80%;
  height: 100vh;
}

.about img {
  position: relative;
  float: left;
  left: 12em;
  margin-right: 1em;
  margin-top: 0.5em;
  box-shadow: 5px 5px 10px grey
}

h1 {
  position: relative;
  left: 2.2em;
}

h2 {
  max-width: 450px;
  position: absolute;
  transform: translateX(25em);
}

.about p {
  display: flex;
  float: left;
  padding-left: 2.5em;
  text-align: justify;
  margin-bottom: 10px;
  max-width: 23em;
  transform: translate(14em,3em);
}

@media only screen and (min-width: 320px) and (max-width: 768px){
  .about img {
    display: none;
  }

  h1 {
    left: 10%;
  }

  h2 {
    width: 100%;
    transform: translateX(10%);
    position: relative;
    margin-top: -1em;
  }

  .about p {
    display: flex;
    float: left;
    padding:0;
    margin: 0 auto;
    text-align: justify;
    margin-bottom: 1.7em;
    margin-top: -1.5em;
    max-width: 23em;
    transform: translate(2.1em,3em);
  }
}
</style>
