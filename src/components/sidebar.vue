<template>
  <div class="wrapper">
    <div class="menu">
      <button id="toggle" ref="menu" @click="onTranslate" @scroll="fixedMenu">|||</button>
    </div>
    <transition name="fade">
      <div class="sidebar" id="sideBar" v-if="show">
        <button id="closeBtn" @click="onReturn">&times;</button>
        <ul>
          <a href="#header">
            <li class="list">
              Home
            </li>
          </a>
          <a href="#about">
            <li class="list">
              About
            </li>
          </a>
          <a href="#project">
            <li class="list">
              Projects
            </li>
          </a>
          <a data-page="skills" href="#skills">
            <li class="list">
              Skills
            </li>
          </a>
          <a href="#contact">
            <li class="list">
              Contact
            </li>
          </a>
        </ul>
        <div class="social-media">
          <a href="https://www.facebook.com/galoabolicao" target="_blank" class="facebook">
            <i class="fa fa-facebook-f"></i>
          </a>
          <a href="https://www.instagram.com/camilo_parra_galo/" target="_blank" class="instagram">
            <i class="fa fa-instagram"></i>
          </a>
          <a href="https://www.linkedin.com/in/parra-camilo/" target="_blank" class="linkedin">
            <i class="fa fa-linkedin"></i>
          </a>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  props: {},
  data () {
    return {
      show: false,
      translate: false
    }
  },
  methods: {
    onTranslate () {
      if (!this.show && !this.translate) {
        this.show = true
        this.translate = true
        this.$emit('onTranslate', this.translate)
      } else {
        this.show = false
        this.translate = false
      }
    },
    onReturn () {
      this.show = false
      this.translate = false
      this.$emit('onReturn', this.translate)
    },
    fixedMenu () {
      this.$refs.menu.className = 'fixedMenu'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.fade-enter-active {
  -webkit-transition: all 0.5s;
  -o-transition: all 0.5s;
  transition: all 0.5s;
}
.fade-leave-active {
  -webkit-transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
  -o-transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.fade-enter, .fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  -webkit-transform: translateX(10px);
  -ms-transform: translateX(10px);
  transform: translateX(10px);
  opacity: 0;
}
.menu {
  text-align: left;
  height: 35px;
  position: absolute;
}
.list:hover {
  color: var(--secondary);
}
#toggle {
  outline: none;
  top: 30px;
  left: 30px;
  font-weight: 800;
  position: fixed;
  width: 35px;
  font-size: 3em;
  color: var(--secondary);
  cursor: pointer;
  border: none;
  background: none;
  -webkit-text-stroke: 1px var(--text-title);
  -moz-text-stroke: 1px var(--text-title);
  z-index: -1;
  transition: all 0.5s;
  -webkit-transition: all 0.25s;
  -moz-transition: all 0.25s;
}
#toggle:hover {
  transform: rotate(90deg);
  -webkit-transform: rotate(90deg);
  color: var(--primary);
  -webkit-text-stroke: 1px var(--text-title);
  -moz-text-stroke: 1px var(--text-title);
}
#closeBtn {
  outline: none;
  padding: 0;
  left: 20%;
  top: -5px;
  font-size: 4em;
  color: var(--text-title);
  cursor: pointer;
  border: none;
  background: none;
  text-align: right;
  position: relative;
  z-index: 1;
  transition: all 0.35s;
  -webkit-transition: all 0.25s;
  -moz-transition: all 0.25s;
}
#closeBtn:hover {
  color: var(--secondary);
  -webkit-text-stroke: 2px var(--text-title);
  -moz-text-stroke: 2px var(--text-title);
}
.wrapper {
  display: flex;
  position: relative;
  z-index: 1;
}
.wrapper .sidebar {
  /* display: none; */
  position: fixed;
  width: 20%;
  height: 100%;
  background: var(--primary);
  padding: 30px 0;
  box-shadow: 5px 5px 10px grey;
  transition: all 0.25s;
  -webkit-transition: all 0.25s;
  /* -webkit-transition: all 0.4s ease-in-out;
  -o-transition: all 0.4s ease-in-out;
  transition: all 0.4s ease-in-out; */
}
.wrapper .sidebar ul li {
  display: flex;
  padding: 15px;
  border-bottom: 1px solid var(--text-title);
  border-top: 1px solid var(--text-title);
  left: 25px;
  cursor: pointer;
  color: var(--text-title);
  font-size: 1em;
  transition: all 0.25s;
  -webkit-transition: all 0.25s;
}
.wrapper .sidebar ul li a {
  color: var(--text-title);
  display: block;
}
.wrapper .sidebar ul li a .fa {
  position: absolute;
  width: 25px;
  padding: 5px;
  margin-top: 10px;
  color: var(--primary);
}
.wrapper .sidebar ul li:hover {
  background: var(--secondary);
  color: #f3f5f9;
  font-size: 1.5em;
}
.wrapper .sidebar ul li:hover a {
  color: var(--primary);
}
.wrapper .sidebar ul li:hover a .fa {
  color: var(--text-title);
}
.facebook:hover {
  background: #0000ff;
  color: var(--primary);
  font-size: 1.5em;
}
.instagram:hover {
  background: #00ff00;
  color: var(--primary);
  font-size: 1.5em;
}
.linkedin:hover {
  background: #ff0000;
  color: var(--primary);
  font-size: 1.5em;
}
.wrapper .sidebar .social-media {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  -webkit-transition: all 0.4s cubic-bezier(0.6, -0.28, 0.735, 0.045);
  -o-transition: all 0.4s cubic-bezier(0.6, -0.28, 0.735, 0.045);
  transition: all 0.4s cubic-bezier(0.6, -0.28, 0.735, 0.045);
}
.wrapper .sidebar .social-media a {
  display: block;
  width: 40px;
  background: var(--primary);
  height: 40px;
  line-height: 40px;
  text-align: center;
  margin: 0 5px;
  border-top-right-radius: 5px;
  border-top-left-radius: 5px;
}
.wrapper .sidebar .social-media a .fa {
  color: var(--text-title);
}
.wrapper .sidebar .social-media:hover a:nth-child(1) {
  width: 45px;
  height: 45px;
  padding-top: 5px;
  color: var(--primary);
  font-size: 1.5em;
  background: #3d559d;
}
.wrapper .sidebar .social-media:hover a:nth-child(2) {
  width: 45px;
  height: 45px;
  padding-top: 5px;
  color: var(--primary);
  font-size: 1.5em;
  background: #661366;
}
.wrapper .sidebar .social-media:hover a:nth-child(3) {
  width: 45px;
  height: 45px;
  padding-top: 5px;
  color: var(--primary);
  font-size: 1.5em;
  background: #4e4a4e;
}
.wrapper .main-content {
  width: 100%;
}
.wrapper .main-content header {
  height: 100vh;
  padding: 20px;
  background: var(--secondary);
  color: #717171;
  border-bottom: 1px solid var(--border);
}

@media all and (min-width: 320px) and (max-width: 768px){
  .wrapper .sidebar {
    position: fixed;
    width: 50%;
    height: 100%;
    transition: all 0.25s;
    -webkit-transition: all 0.25s;
  }

  .wrapper .sidebar ul li:hover {
    font-size: 1.2em;
  }
  .menu {
    position: fixed;
    margin-top: 0;
  }

  #toggle {
    font-size: 2em;
  }

  .fixedMenu {
    position: fixed;
    margin-top: 30px;
    background: red;
  }

  #closeBtn {
    left: 40%;
    padding-top: 0;
    margin-top: 0;
    margin-right: 20px;
  }

.wrapper .sidebar ul li {
  display: block;
  padding: 1em;
}
}
</style>
