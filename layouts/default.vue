<template>
  <v-app :class="this.$route.name">
    <v-navigation-drawer :class="this.$route.name" fixed floating app width="100">
      <v-list flat class="mt-6">
        <v-list-item          
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          active-class="white--text navigation-item-active"
          :class="`${item.color}--text`"
          router
          exact
        >
          <v-list-item-content>
            <v-list-item-title             
              class="navigation-item-title"
            >
            {{ item.title.toUpperCase() }}
            </v-list-item-title>

          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="clipped = !clipped"
      >
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="fixed = !fixed"
      >
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar> -->
    <v-main>
      <v-container>
        <v-row>
          <v-col>
            <v-hover v-slot="{ hover }">
            <v-btn
            text                                                            
            nuxt              
            x-large          
            fixed
            to="/"
            id="home-btn"            
            :class="hover ? 'disco-title' : ''"
            class="text-h3 mt-10 pr-0"                          
              >
              <span v-if="$route.name === 'index'">Silvia Righetti</span>              
                <v-img
                  style="position: fixed; right: 80px; top: 25px"
                  :src="hover ? '/gallinaDance.GIF' : '/gallina.png'"
                  max-height="300"
                  max-width="150"
                ></v-img>                                                                                               
            </v-btn>                                               
            </v-hover>              
          </v-col>          
        </v-row>
        <Nuxt />
      </v-container>
    </v-main>
    <!-- <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light> mdi-repeat </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer> -->
    <!-- <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer> -->
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-apps",
          title: "Work",
          to: "/work",
          color: "work",
        },
        {
          icon: "mdi-apps",
          title: "Personal",
          to: "/personal",
          color: "personal",
        },
        {
          icon: "mdi-apps",
          title: "About",
          to: "/about",
          color: "about",
        },
        {
          icon: "mdi-apps",
          title: "Contact",
          to: "/contact",
          color: "contact",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js",
    };
  },
};
</script>

<style lang="scss">
@import '@/assets/scss/animations.scss';

#navigation-drawer {
  //font-family: "Silvia Font" !important;  
}

#home-btn {
  //font-family: "Silvia Font" !important;  
  font-weight: normal;  
  right: 240px; 
  top: 25px; 
  height: inherit;
}

#home-btn::before{
  display: none;
}

.navigation-item-title {
  //font-family: "Silvia Font" !important;  
  font-weight: bold;
  font-size: 195% !important;
  writing-mode: vertical-lr;
}

.disco-title:hover {
-webkit-animation:rainbow 3s infinite;
-ms-animation:rainbow 3s infinite;
-o-animation:rainbow 3s infinite;
animation:rainbow 3s ease-in infinite;    
}
</style>