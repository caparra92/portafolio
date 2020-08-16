<template>
  <div class="flex w-full h-auto py-5 justify-center items-center">
    <form
      class="flex flex-col bg-white w-full p-5 justify-center items-center"
      ref="formEmail"
      @submit.prevent="sendEmail"
    >
      <h1 class="text-center">Get in touch</h1>
      <input
        type="text"
        class="border-none resize-none outline-none py-3 px-0 text-sm w-5/6 m-2 text-blue-900 transition-all duration-300 border-b focus:border-purple-700"
        v-model="name"
        placeholder="Name"
      />
      <input
        type="email"
        class="border-none resize-none outline-none py-3 px-0 text-sm w-5/6 m-2 text-blue-900 transition-all duration-300 border-b focus:border-purple-700"
        v-model="email"
        placeholder="Email"
      />
      <textarea
        v-model="message"
        class="border-none resize-none outline-none py-3 px-0 text-sm w-5/6 m-2 text-blue-900 transition-all duration-300 border-b focus:border-purple-700"
        cols="20"
        rows="3"
        placeholder="Message"
      ></textarea>
      <button type="submit" class="btn btn-purple">Send</button>
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
</style>
