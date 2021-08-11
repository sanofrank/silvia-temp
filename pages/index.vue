<template>
  <v-row>
    <div class="posts"></div>  
    <div class="posts"></div>  
    <div class="posts"></div>  
    <div class="posts"></div>  
    <div class="posts"></div>  
    <div class="posts"></div>  
  </v-row>
</template>

<script>
export default {
  methods: {
    // function that returns a random number between a min and max
    getRandomNumber(min, max) {
      return Math.random() * (max - min) + min;
    },
  },
  mounted() {
    var divs = document.getElementsByClassName("posts");
    // get window width and height
    var winWidth = window.innerWidth;
    var winHeight = window.innerHeight;

    // i stands for "index". you could also call this banana or haircut. it's a variable
    for (var i = 0; i < divs.length; i++) {
      // shortcut! the current div in the list
      var thisDiv = divs[i];

      // get random numbers for each element
      let randomTop = this.getRandomNumber(0, winHeight);
      let randomLeft = this.getRandomNumber(0, winWidth);

      // update top and left position
      thisDiv.style.top = randomTop + "px";
      thisDiv.style.left = randomLeft + "px";
    }
  },
};
</script>

<style lang="scss" scoped>
div {
  color: white;
  background-color: purple;
  position: absolute;
  height: 300px;
  width: 200px;
  top: 100px;
  left: 100px;
}
</style>