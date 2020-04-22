<template>
  <div class='card'>
    <img :src="require('../assets/'+image)" alt=image ref="image" :class="{ 'add-top' : addTop}" />
    <div class='card-container'>
      <h1 class='card-title'><b>{{title}}</b></h1>
      <p v-text='description'></p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    image: {
      type: String,
      default: 'default.png'
    },
    title: {
      type: String,
      default: 'ImageTitle'
    },
    description: {
      type: String,
      default: 'Image description'
    },
    addTop: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped>
.card {
  width: 10em;
  height: 20em;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  padding: .2em .5em;
  transition: all 0.5s cubic-bezier(0.075, 0.82, 0.165, 1);
  margin: 0 .9em;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.card img {
  width: 100%;
}

.card-container {
  padding: 2px 16px;
  font-size: 0.8em;
}

.add-top {
  position: relative;
  padding-top: 3em;
  margin: 2em 0;
  top: 50%;
}

@media only screen and (min-width: 320px) and (max-width: 768px){
.card {
  width: 8em;
  height: 15em;
  padding: .2em .2em;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.card img {
  width: 100%;
}

.card-container {
  padding: 2px 8px;
  font-size: 0.8em;
}

.add-top {
  position: relative;
  padding-top: 1em;
  margin: 1em 0;
  top: 50%;
}

}

</style>
