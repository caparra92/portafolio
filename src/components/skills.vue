<template>
  <section class="container skills" id="skills">
    <h1 class="title">Skills</h1>
    <p>What would you like for your next project? These are some awesome tecnologies for your website or information system</p>
    <ul class="list-items">
      <li>
        <figure>
          <img :src="require('../assets/laravel.png')" alt="laravel" width="100px" height="100px" />
          <figcaption>Laravel</figcaption>
        </figure>
      </li>
      <li>
        <figure>
          <img :src="require('../assets/javascript.png')" alt="javascript" width="100px" height="100px" />
          <figcaption>Javascript</figcaption>
        </figure>
      </li>
      <li>
        <figure>
          <img :src="require('../assets/java.png')" alt="java" width="100px" height="100px" />
          <figcaption>Java</figcaption>
        </figure>
      </li>
      <li>
        <figure>
          <img :src="require('../assets/html5.png')" alt="Html5" width="100px" height="100px" />
          <figcaption>HTML5</figcaption>
        </figure>
      </li>
    </ul>
    <p v-text="p1"></p>
    <p>You can get more details in the contact section or click <a href="#contact" class="here">here</a></p>
  </section>
</template>

<script>
export default {
  name: 'Skills',
  props: {
    p1: {
      type: String,
      default: 'Contact us for futher information about what of these you should choose.'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.skills {
  background: #5f5594;
  color: #fff;
  height: 100vh;
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
</style>
