<template>
  <div class="flex h-auto justify-center items-center">
    <form
      class="contact-form"
      ref="formEmail"
      @submit.prevent="sendEmail"
    >
      <div class="button-container">
        <button type="button" class="btn btn-purple">
          <i class="fa fa-envelope"></i>
          Email
        </button>
        <button type="button" class="btn btn-purple">
          <i class="fa fa-file"></i>
          Resume
        </button>
      </div>
    </form>
  </div>
</template>
<script>
import emailjs from 'emailjs-com'

export default {
  name: 'FormContact',
  data () {
    return {
      email: '',
      reply_to: 'reply_to_value',
      name: '',
      to_name: 'Camilo',
      message: ''
    }
  },
  created () {
    emailjs.init('user_7t0xjgXg5htc8keotPfy0')
  },
  methods: {
    sendEmail (e) {
      const data = {
        email: this.email,
        name: this.name,
        to_name: 'Camilo',
        message: this.message
      }
      emailjs
        .send('gmail', 'contactEmail', data)
        .then((res) => {
          this.$refs.formEmail.reset()
        })
        .catch((error) => {
          throw error
        })
    }
  }
}
</script>
<style scoped>
  .contact-form {
    width: 100%;
    margin: 0;
    padding: 0;
  }

  .contact-form .btn {
    width: 100%;
    align-self: center;
    margin: 15px 0 5px 10px;
    outline: none;
  }

  .contact-form .btn:nth-child(2) {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .contact-form .btn:nth-child(2) i {
    margin-right: 5px;
    padding-bottom: 4px;
  }

  .button-container {
    display: flex;
  }

  @media all and (min-width: 320px) and (max-width: 768px){

  .contact-form .btn {
    margin: 15px 0 0 10px;
  }

  }
</style>
