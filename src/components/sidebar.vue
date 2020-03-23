<template>
  <div class="wrapper">
    <div class="menu">
      <button id="toggle" @click="show = true">&#9776;</button>
    </div>
    <transition name="fade">
      <div class="sidebar" id="sideBar" v-if="show">
        <button id="closeBtn" @click="show = !show"><i class="fa fa-bars"></i></button>
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
            <i class="fa fa-facebook-f"></i>
          </a>
          <a href="#">
            <i class="fa fa-instagram"></i>
          </a>
          <a href="#">
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
      show: false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.slide-fade-enter-active {
  -webkit-transition: all 0.3s ease;
  -o-transition: all 0.3s ease;
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  -webkit-transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
  -o-transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
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
  left: 25px;
  position: fixed;
  width: 35px;
  font-size: 35px;
  color: #413968;
  cursor: pointer;
  border: none;
  background: none;
}
#toggle:hover{
  color: #fff;
  -webkit-text-stroke: 1px #000;
}
#closeBtn {
  padding: 5px;
  width: 35px;
  font-size: 35px;
  color: #fff;
  cursor: pointer;
  border: none;
  background: none;
  text-align: right;
  display: inline-block;
  position: relative;
  left: 75px;
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
  background: #594f8d;
}
.wrapper .sidebar ul li:hover a {
  color: #fff;
}
.wrapper .sidebar ul li:hover a .fa {
  color: #fff;
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
