<template>
  <section class="container contact" id="contact">
    <article class="article">
      <h1 class="title" v-text = 'title'></h1>
      <p v-text = 'contactP'></p>
      <p>{{calcTime(city,zone) + contactP2}}</p>
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
    contactP: {
      type: String,
      default: 'You can contact us for email through caparra92@gmail.com or in the social media section below the menu'
    },
    contactP2: {
      type: String,
      default: ", but i'm get ready for contact by e-mail or social media"
    },
    city: {
      type: String,
      default: 'Pasto'
    },
    zone: {
      type: String,
      default: '-5'
    },
    calcTime: {
      type: Function,
      default (city, offset) {
        // creamos el objeto Date (la selecciona de la máquina cliente)
        const d = new Date()
        // lo convierte  a milisegundos
        // añade la dirferencia horaria
        // recupera la hora en formato UTC
        const utc = d.getTime() + (d.getTimezoneOffset() * 60000)
        // crea un nuevo objeto Date usando la diferencia dada.
        const nd = new Date(utc + (3600000 * offset))
        // devuelve la hora como string.
        return 'Is ' + nd.getHours() + ':' + nd.getMinutes() + ':' + nd.getSeconds() + ' in ' + city
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
  max-width: 1055px;
  margin: 0 auto;
  height: 100vh;
}
.contact p {
  max-width: 450px;
}
</style>
