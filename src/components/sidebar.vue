<template>
  <div class="wrapper">
    <div class="menu">
      <button id="toggle" @click="onTranslate">|||</button>
    </div>
    <transition name="fade">
      <div class="sidebar" id="sideBar" v-if="show">
        <button id="closeBtn" @click="onReturn">&times;</button>
        <ul>
          <a href="#header">
            <li class="list">
              <i class="fa fa-home"></i>Home
            </li>
          </a>
          <a href="#about">
            <li class="list">
              <i class="fa fa-user"></i>About
            </li>
          </a>
          <a href="#project">
            <li class="list">
              <i class="fa fa-folder"></i>Projects
            </li>
          </a>
          <a href="#skills">
            <li class="list">
              <i class="fa fa-tasks"></i>Skills
            </li>
          </a>
          <a href="#contact">
            <li class="list">
              <i class="fa fa-address-book"></i>Contact
            </li>
          </a>
        </ul>
        <div class="social-media">
          <a href="#">
            <i class="fa fa-facebook-f facebook"></i>
          </a>
          <a href="#">
            <i class="fa fa-instagram instagram"></i>
          </a>
          <a href="#">
            <i class="fa fa-linkedin linkedin"></i>
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
  color:#fff;
}
#toggle {
  top: 30px;
  left: 30px;
  font-weight: 800;
  position: fixed;
  width: 35px;
  font-size: 3em;
  color: #413968;
  cursor: pointer;
  border: none;
  background: none;
  transition: all 0.5s;
  -webkit-transition: all 0.25s;
}
#toggle:hover {
  transform: rotate(90deg);
  -webkit-transform: rotate(90deg);
  color: #fff;
  -webkit-text-stroke: 1px #000;
}
#closeBtn {
  padding: 0;
  left: 20%;
  top: -5px;
  font-size: 4em;
  color: #fff;
  cursor: pointer;
  border: none;
  background: none;
  text-align: right;
  position: relative;
  transition: all 0.35s;
  -webkit-transition: all 0.25s;
}
#closeBtn:hover {
  color: #fff;
  -webkit-text-stroke: 2px #000;
}
.wrapper {
  display: flex;
  position: relative;
}
.wrapper .sidebar {
  /* display: none; */
  position: fixed;
  width: 20%;
  height: 100%;
  background: #413968;
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
  border-bottom: 1px solid rgba(0, 0, 0, 0.05);
  border-top: 1px solid rgba(225, 225, 225, 0.05);
  left: 25px;
  cursor: pointer;
  color: #bdb8d6;
  font-size: 1em;
  transition: all 0.25s;
  -webkit-transition: all 0.25s;
}
.wrapper .sidebar ul li a {
  color: #bdb8d6;
  display: block;
}
.wrapper .sidebar ul li a .fa {
  position: absolute;
  width: 25px;
  padding: 5px;
  margin-top: 10px;
  color: #bdb8d6;
}
.wrapper .sidebar ul li:hover {
  background: #fff;
  color: #413968;
  font-size: 1.5em;
}
.wrapper .sidebar ul li:hover a {
  color: #fff;
}
.wrapper .sidebar ul li:hover a .fa {
  color: #fff;
}
.facebook:hover {
  background: #0000ff;
  color: #fff;
  font-size: 1.5em;
}
.instagram:hover {
  background: #00ff00;
  color: #fff;
  font-size: 1.5em;
}
.linkedin:hover {
  background: #ff0000;
  color: #fff;
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
  background: #594f8d;
  height: 40px;
  line-height: 40px;
  text-align: center;
  margin: 0 5px;
  border-top-right-radius: 5px;
  border-top-left-radius: 5px;
}
.wrapper .sidebar .social-media a .fa {
  color: #fff;
}
.wrapper .sidebar .social-media:hover a {
  width: 45px;
  height: 45px;
  padding-top: 5px;
  color: #bdb8d6;
  font-size: 25px;
  background: #5f5594;
}
.wrapper .main-content {
  width: 100%;
}
.wrapper .main-content header {
  height: 100vh;
  padding: 20px;
  background: #fff;
  color: #717171;
  border-bottom: 1px solid #e0e4e8;
}
</style>
