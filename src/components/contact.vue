<template>
  <section class="container contact" id="contact">
    <article class="article">
      <h1 class="title" v-text="title"></h1>
      <div class="form">
        <slot></slot>
        <p>
          <i class="fa fa-clock-o"></i>
          {{calcTime(city,zone) + contactP2}}
        </p>
        <slot name="textLine"></slot>
      </div>
      <div class="panel">
        <li class="fa fa-facebook"></li>
        <li class="fa fa-instagram"></li>
        <li class="fa fa-linkedin"></li>
        <li class="fa fa-envelope"></li>
      </div>
    </article>
  </section>
</template>

<script>
export default {
  name: 'Contact',
  props: {
    title: {
      type: String,
      default: 'Contact'
    },
    contactP2: {
      type: String,
      default: ", but i'm get ready for contact by e-mail or social media."
    },
    city: {
      type: String,
      default: 'Londrina'
    },
    zone: {
      type: String,
      default: '-3'
    },
    calcTime: {
      type: Function,
      default (city, offset) {
        // creamos el objeto Date (la selecciona de la máquina cliente)
        const d = new Date()
        // lo convierte  a milisegundos
        // añade la dirferencia horaria
        // recupera la hora en formato UTC
        const utc = d.getTime() + d.getTimezoneOffset() * 60000
        // crea un nuevo objeto Date usando la diferencia dada.
        const nd = new Date(utc + 3600000 * offset)
        // devuelve la hora como string.
        return (
          'Is ' +
          nd.getHours() +
          ':' +
          nd.getMinutes() +
          ':' +
          nd.getSeconds() +
          ' in ' +
          city
        )
        // console.log(calcTime('Pasto', '-5'))
      }
    }
  },
  methods: {}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.contact {
  margin: 0 auto;
  height: 100vh;
}

.contact p {
  color: #000;
  padding: 1em;
}

.form {
  position: relative;
  float: left;
  background: #fff;
  max-width: 22em;
  left: 7em;
  top: 1em;
  border-radius: 0.3em;
}

.panel {
  position: absolute;
  width: 50%;
}

.panel .fa {
  font-size: 5em;
  transition: all .5s ease-out;
}

.panel .fa-facebook{
  position: absolute;
  color: #3d559d;
  left: 9em;
}

.panel .fa-instagram{
  position: absolute;
  color: #8a3ab9;
  left: 10.5em;
  top: 2em;
}

.panel .fa-linkedin{
  position: absolute;
  color: #000;
  left: 7em;
  top: 1.5em;
}

.panel .fa-envelope{
  position: absolute;
  color: rgb(238, 36, 36);
  left: 8.5em;
  top: 1.5em;
}

@media only screen and (min-width: 320px) and (max-width: 768px){

h1 {
  margin-top: 3em;
  padding-top: 10px;
}
.form {
  position: inherit;
  float: none;
  display: block;
  padding: 0;
  margin: 0 auto;
}

.panel {
  display: none;
}
}
</style>
