<template>
  <header class="header" id="header">
    <div class="name">
      <h1 data-text="<Web developer/>">.Web developer.</h1>
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
  background-image: linear-gradient(rgba(81, 17, 185, 0.8), rgba(0,0,0,0.9)), url('../assets/webdev.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  border-bottom: 1px solid #e0e4e8;
}

.name {
  position: relative;
  font-size: 1em;
  top: 50%;
  left: 50%;
  margin: 0;
  padding: 0;
  transform: translate(-50%,-50%);
  text-transform: uppercase;
  color: transparent;
}

h1 {
  position: relative;
  display: inline;
  letter-spacing: 5px;
}

h1:before {
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

/* .layer {
  position: absolute;
  width: 100%;
  height: 100vh;
  top: 0;
  left: 0;
  padding: 20px;
  padding: 20px;
  background: #000;
  opacity: 0.5;
} */
</style>
