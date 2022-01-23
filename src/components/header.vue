<template>
  <header class="header" id="header">
    <div class="change-theme-container">
      <label class="switch">
        <input type="checkbox" class="switch" @click="changeTheme()" />
        <span class="slider-switch"></span>
      </label>
      <!-- <span class="sun" @click="changeTheme()">
        <i class="fa fa-sun-o"></i>
      </span>
      <span class="moon" @click="changeTheme()">
        <i class="fa fa-moon-o"></i>
      </span> -->
    </div>
    <div class="name">
      <h1>camilo parra</h1>
      <h4 data-text="web developer">web developer</h4>
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
  },
  data () {
    return {
      clicked: false,
      root: null
    }
  },
  mounted () {
    this.root = document.documentElement
  },
  methods: {
    changeTheme () {
      this.clicked = !this.clicked
      if (this.clicked) {
        this.root.style.setProperty('--primary', '#2c2c2c')
        this.root.style.setProperty('--text-title', '#f3f5f9')
      } else {
        this.root.style.setProperty('--primary', '#f3f5f9')
        this.root.style.setProperty('--text-title', '#2c2c2c')
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header {
  height: 100vh;
  padding: 20px;
  background-image: linear-gradient(var(--primary), rgba(0, 0, 0, 0.9)),
    url("../assets/webdev.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  border-bottom: 1px solid var(--secondary);
}

.change-theme-container {
  position: absolute;
  right: 0;
  top: 44px;
  padding: 0 15px 0;
  margin-right: 10px;
  display: flex;
  width: 12%;
  align-items: flex-start;
  justify-content: space-around;
}

.change-theme-container span:hover {
  transform: scale(1.2);
}

.change-theme-container span:nth-child(1):hover {
  background: #dada40;
  color: var(--text-title);
}

.change-theme-container span:nth-child(2):hover {
  background: #838382;
  color: var(--text-title);
}

.switch {
  position: relative;
  margin: 10px;
  display: inline-block;
  width: 60px;
  height: 34px;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider-switch {
  position: absolute;
  cursor: pointer;
  border-radius: 34px;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  background-color: var(--border);
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider-switch:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  border-radius: 50%;
  left: 4px;
  bottom: 4px;
  background-color: var(--primary);
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

input:checked + .slider-switch {
  background-color: var(--secondary);
}

input:focus + .slider-switch {
  box-shadow: 0 0 1px #2196f3;
}

input:checked + .slider-switch:before {
  -webkit-transform: translateX(26px);
  -moz-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

.name {
  position: relative;
  font-size: 2em;
  top: -5em;
  left: 50%;
  margin: 0;
  padding: 0;
  transform: translate(-50%, -50%);
  text-transform: uppercase;
  color: #f3f5f9;
  animation: fall 2s cubic-bezier(0, 0.9, 0.3, 1.2) forwards;
  animation-delay: 1s;
  /* color: transparent; */
}

h1 h2 {
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
@media all and (min-width: 320px) and (max-width: 768px) {
  header {
    padding: 0;
    height: 100vh;
  }

  .change-theme-container {
    margin-right: 10px;
    width: 25%;
  }

  .change-theme-container span {
    width: 1.9em;
    height: 1.3em;
  }

  .name {
    font-size: 1em;
    /* color: transparent; */
  }

  .slider-switch {
    border-radius: 13px;
  }

  .slider-switch::before {
    height: 18px;
    width: 18px;
  }

  input:checked + .slider-switch:before {
    -webkit-transform: translateX(16px);
    -moz-transform: translateX(16px);
    -ms-transform: translateX(16px);
    transform: translateX(16px);
  }
}
</style>
