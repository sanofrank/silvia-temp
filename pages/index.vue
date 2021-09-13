<template>
  <v-row>
    <v-col cols="12" id="head">     
    </v-col>
    <template>
        <v-col sm="6" lg="4" cols="12" class="col-post" v-for="post in posts" :key="post.id">
          <v-sheet class="post d-flex align-center justify-center" :class="post.type" elevation="2">
            {{ post.title + post.id }}
          </v-sheet>
        </v-col>
    </template>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {
          id: "01",
          type: 'work',
          title: 'WORK',          
        },
        {
          id: "02",
          type: 'work',
          title: 'WORK',          
        },
        {
          id: "03",
          type: 'personal',
          title: 'PERSONAL',          
        },
        {
          id: "04",
          type: 'work',
          title: 'WORK',          
        },
        {
          id: "05",
          type: 'personal',
          title: 'PERSONAL',          
        },
        {
          id: "06",
          type: 'work',
          title: 'WORK',          
        },
        {
          id: "07",
          type: 'personal',
          title: 'PERSONAL',          
        },
        {
          id: "08",
          type: 'work',
          title: 'WORK',          
        },
        {
          id: "09",
          type: 'work',
          title: 'WORK',          
        },
        {
          id: "10",
          type: 'personal',
          title: 'PERSONAL',          
        },
        {
          id: "11",
          type: 'work',
          title: 'WORK',          
        },
        {
          id: "12",
          type: 'personal',
          title: 'PERSONAL',          
        },
        {
          id: "13",
          type: 'work',
          title: 'WORK',          
        },
        {
          id: "14",
          type: 'personal',
          title: 'PERSONAL',          
        }        
      ]      
    }
  },
  methods: {
    // function that returns a random number between a min and max
    getRandomNumber(min, max) {
      return Math.random() * (max - min) + min;
    },
  },
  mounted() {
    var divs = document.getElementsByClassName("post");
    var cols = document.getElementsByClassName("col-post");
    // get window width and height    

    // i stands for "index". you could also call this banana or haircut. it's a variable
    for (var i = 0; i < divs.length; i++) {
      // shortcut! the current div in the list
      var thisDiv = divs[i];

      var divWidth = cols[i].getBoundingClientRect().width - thisDiv.getBoundingClientRect().width;
      var divHeight = cols[i].getBoundingClientRect().height - thisDiv.getBoundingClientRect().height;

      // get random numbers for each element
      let randomTop = this.getRandomNumber(0, divHeight);
      let randomLeft = this.getRandomNumber(0, divWidth);
      
      // update top and left position
      thisDiv.style.marginTop = randomTop + "px";
      thisDiv.style.marginLeft = randomLeft + "px";
    }
  },
};
</script>

<style lang="scss" scoped>
@import '@/assets/variables.scss';

#head {
  height: 150px;
}

.col-post {
  //border: solid black;
  //background-color: purple;
  height: 30em;
}

.post {
  position: absolute;  
  color: white;  
}

.work{
  background-color: $work-color;
  height: 300px;
  width: 200px;
}

.personal{
  height: 200px;
  width: 300px;
  background-color: $personal-color;
}
</style>