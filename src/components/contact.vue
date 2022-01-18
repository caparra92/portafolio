<template>
  <section class="container" id="contact">
    <h1 class="title">Contact</h1>
    <div class="contact-container">
      <div class="text-container">
        <slot></slot>
        <p class="py-4 text-black">
          <i class="fa fa-clock-o"></i>
          {{calcTime(city,zone) + contactP2}}
        </p>
        <slot name="textLine"></slot>
      </div>
      <div class="form-contact">
        <FormContact/>
      </div>
    </div>
  </section>
</template>

<script>
import FormContact from './formContact'

export default {
  name: 'Contact',
  components: {
    FormContact
  },
  props: {
    contactP2: {
      type: String,
      default: ", but i'm get ready for contact by e-mail or social media."
    },
    city: {
      type: String,
      default: 'Bogotá'
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
.container {
  margin: 0 auto;
}

.contact-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
}

.contact-container p {
  max-width: 80%;
  margin: 0 auto;
}

.text-container {
  margin-bottom: 30px;
}

.text-container p {
  color: var(--text-title);
}

.contact-form {
  display: flex;
  flex-direction: column;
}

@media all and (min-width: 320px) and (max-width: 768px){

h1 {
  margin-top: 1em;
}

.article {
  display: flex;
  flex-flow: column;
  align-items: center;
}

.form {
  display: none;
  /* width: 80%;
  position: inherit;
  float: none;
  display: block;
  padding: 0;
  margin: 0 auto; */
}

.contact-form {
  width: 100%;
  margin: 0 auto;
}

.contact-container {
  flex-direction: column;
}

}
</style>
