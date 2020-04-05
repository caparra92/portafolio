<template>
  <section class="container about" id="about">
    <h1 class="title">About</h1>
    <img :src="require('../assets/camilo.jpg')" alt="Camilo" width="400px" height="400px" />
    <p>I was born in 1992 in Pasto city of Colombia, degree in computer science of the University of Nariño in 2017, he really likes work with web development specially with javascript and HTML tecnologies.</p>
    <p>I worked in diferents areas as teaching office packages and basic concepts of information technologies.</p>
    <p>My experience includes technician support, informatic teaching skills, web development of profesional websites and also information systems. </p>
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
  height: 100vh;
}

.about img {
  position: relative;
  float: left;
  left: 15%;
  margin-right: 20px;
  margin-top: 10px;
  box-shadow: 5px 5px 10px grey
}

.about p {
  position: relative;
  margin-left: 45%;
  padding-left: 50px;
  margin-right: 200px;
  text-align: justify;
  margin-bottom: 10px;
}
</style>
