<template>
    <div class="flex w-full h-auto py-5 justify-center items-center bg-red-100">
        <form class="flex flex-col bg-white w-full p-5 justify-center items-center">
            <h1 class="text-center">Get in touch</h1>
            <input type="text" class="border-none resize-none outline-none py-3 px-0 text-sm w-5/6 m-2 text-blue-900 transition-all duration-300 border-b focus:border-purple-700" id="name" placeholder="Name">
            <input type="email" class="border-none resize-none outline-none py-3 px-0 text-sm w-5/6 m-2 text-blue-900 transition-all duration-300 border-b focus:border-purple-700" id="email" placeholder="Email">
            <textarea id="message" class="border-none resize-none outline-none py-3 px-0 text-sm w-5/6 m-2 text-blue-900 transition-all duration-300 border-b focus:border-purple-700" cols="20" rows="3" placeholder="Message"></textarea>
            <button class="btn btn-purple" value="send">Send</button>
        </form>
    </div>
</template>
<script>
export default {
  name: 'FormContact'
}
</script>
<style scoped>
</style>
