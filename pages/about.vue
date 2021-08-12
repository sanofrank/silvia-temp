<template>
  <v-row class="mt-4">
    <v-col cols="12">
      <Title :title="title" :classes="'text-h1'"/>
    </v-col>
    <v-col md="8" cols="12" class="text-h5">
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut et est enim.
        Donec elementum risus mollis sagittis viverra. Vivamus efficitur
        convallis dolor, sed imperdiet dui rutrum vel. Etiam dapibus ligula
        lobortis purus interdum, gravida mollis elit maximus. Vestibulum id
        eleifend sem. Integer consectetur vitae nunc sed consectetur. In hac
        habitasse platea dictumst. Integer et egestas elit.
      </p>
      <p>
        Nam ligula turpis, tincidunt ut mattis a, mattis sit amet dui. Ut eu
        diam molestie, feugiat odio ut, tincidunt sem. Sed et sem quis nisl
        maximus scelerisque non nec ligula. Nam in sagittis tellus. Ut cursus
        feugiat lacus, at posuere magna consectetur non. Etiam sit amet nisl
        eget erat dictum pellentesque. Curabitur diam augue, rhoncus vel metus
        et, ullamcorper eleifend nisi. Quisque pellentesque ex a nibh ultrices
        vehicula. Aenean eu laoreet mi, eget facilisis velit. Nullam a imperdiet
        risus. Maecenas in nunc et est lacinia maximus. Quisque sit amet
        scelerisque lectus, a viverra ante.
      </p>
    </v-col>
    <v-col md="4" cols="12" class="d-flex justify-center align-center mt-16">
      <v-img src="/about.jpg" max-height="500" max-width="300"> </v-img>
    </v-col>
  </v-row>
</template>

<script>
export default {
    data() {
      return {
        title: 'About',        
      }
    },
    mounted(){
        console.log('about')
        return this.$vuetify.theme.about = true
    }
}
</script>