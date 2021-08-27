<template>
  <v-row class="mt-4">
    <v-col cols="12">
      <Title :title="title" :classes="'text-h1'" />
    </v-col>
    <v-col cols="12" class="body-main">      
        <div style="height: 70vh" class="d-flex align-center">
            <ul>
          <li>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut et est
            enim.
          </li>
          <li>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut et est
            enim.
          </li>
          <li>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut et est
            enim.
          </li>
        </ul>
        </div>        
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      title: "Contact",
    };
  },
};
</script>

<style lang="scss">    
    ul {
        list-style-type: none;
    }    
    
    li:before {
        content: '-'
    }

    li {
        margin: 2em 0;
    }

</style>