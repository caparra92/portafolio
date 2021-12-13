<template>
  <section class="container about" id="about">
    <h1 class="title">About</h1>
    <div class="title-img"><img src="https://i.postimg.cc/wxX1VS5L/portafolio-image.jpg" alt="Camilo" class="md:w-64 md:h-64 lg:w-1/3 lg:h-auto" /></div>
    <div class="about-content">
      <div class="text-content">
      <h2>Camilo Parra, Web Developer</h2>
      <p>I was born in 1992 in Pasto city of Colombia, degree in computer science of the University of Nariño in 2017, he really likes work with web development specially with javascript and HTML tecnologies.</p>
      <p>I worked in diferents areas as teaching office packages and basic concepts of information technologies.</p>
      <p>I'm a teacher for profesion but developer for vocation.</p>
      </div>
    </div>
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
  margin: 0 auto;
  height: 100vh;
}

.title {
  margin-bottom: 0;
}

.about-content {
  display: flex;
  justify-content: space-between;
  margin: 0 auto;
  width: 80%;
}

.text-content {
  text-align: justify;
  margin-left: 1em;
  font-size: 0.8em
}

.about img {
  margin: auto 0;
  box-shadow: 5px 5px 10px grey;
  border-radius: 100%;
  width: 150px;
}

h2 {
  margin: 0 auto;
  width: 100%;
  margin-bottom: 20px;
  text-align: left;
  font-size: 1.4em;
}

.about p {
  display: flex;
  text-align: justify;
  margin-bottom: 10px;
  margin-top: 20px;
  font-size: 1.2em;
}

.title-img {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: center;
}

@media all and (min-width: 320px) and (max-width: 768px){
  .about-content {
    display: flex;
    justify-content: space-between;
    margin: 0 auto;
    width: 100%;
  }
  .text-content {
    text-align: justify;
    margin-left: 0;
    font-size: 0.7em;
    margin-bottom: 20px;
  }

  .about img {
    display: none;
  }

  h2 {
    text-align: center;
    position: relative;
    margin-top: -1em;
  }

  .about p {
    margin: 0 auto;
    position: relative;
    max-width: 80%;
    text-align: justify;
    margin-bottom: 15px;
  }
}

@media all and (min-width: 769px) and (max-width: 1024px){

  .about img {
    height: auto;
    margin-left: 1em;
  }
}

</style>
