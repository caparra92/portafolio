<template>
  <header class="header" id="header">
    <div class="name">
      <h1>camilo parra</h1>
      <h4 data-text='web developer'>web developer</h4>
    </div>
    <!-- <div class="layer"></div> -->
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    title: {
      type: String,
      default: 'Web developer'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header {
  height: 100vh;
  padding: 20px;
  background-image: linear-gradient(rgba(136, 92, 207, 0.8), rgba(0,0,0,0.9)), url('../assets/webdev.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  border-bottom: 1px solid #e0e4e8;
}

.name {
  position: relative;
  font-size: 2em;
  top: -5em;
  left: 50%;
  margin: 0;
  padding: 0;
  transform: translate(-50%,-50%);
  text-transform: uppercase;
  color: #fff;
  animation: fall 2s cubic-bezier(0, 0.9, 0.3, 1.2) forwards;
  animation-delay: 0.8s;
  /* color: transparent; */
}

h1 h2{
  position: relative;
  display: inline;
  letter-spacing: 5px;
}

h2 {
  animation-delay: 1s;
}

h4 {
  font-size: 1.5em;
}

@keyframes fall {
  100% {
    top: 50%;
  }
}

/* h2:before {
  position: absolute;
  content: attr(data-text);
  top: 0;
  padding-bottom: 5px;
  left: 50%;
  letter-spacing: 1px;
  transform: translate(-50%,-50%);
  width: 100%;
  height: 100%;
  color: #fff;
  overflow: hidden;
  white-space: nowrap;
  border-right: 1px solid #000;
  -webkit-animation: letterWriting 3s infinite steps(16);
          animation: letterWriting 3s infinite steps(16);
}

@keyframes letterWriting {
  0% {
    width: 0;
  }
  50%,75% {
    width: 100%;
  }

  100% {
    width: 0;
  }
}
 */
@media all and (min-width: 320px) and (max-width: 768px){

  header {
    padding: 0;
    height: 100vh;
  }

  .name {
    font-size: 1em;
  /* color: transparent; */
  }
}
</style>
