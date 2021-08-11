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
              v-text="item.title"              
              class="navigation-item-title text-h3"
            />
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
            <v-btn
            text                                                            
            nuxt              
            x-large          
            fixed
            to="/"
            id="home-btn"            
            class="text-h1 mt-2 pr-0"                          
              >
              <span v-if="this.$vuetify.breakpoint.mdAndUp">Silvia Righetti</span>              
              <v-img
                  style="position: fixed; right: 80px; top: 25px"
                  src="/sLogo.png"
                  max-height="280"
                  max-width="150"
                ></v-img>                                                                                               
            </v-btn>                                               
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
          color: "green",
        },
        {
          icon: "mdi-apps",
          title: "Personal",
          to: "/personal",
          color: "yellow",
        },
        {
          icon: "mdi-apps",
          title: "About",
          to: "/about",
          color: "red",
        },
        {
          icon: "mdi-apps",
          title: "Contact",
          to: "/contact",
          color: "blue",
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
#home-btn {
  text-transform: none; 
  right: 260px; 
  top: 25px; 
  height: inherit;
}

#home-btn::before{
  display: none;
}

.navigation-item-title {
  writing-mode: vertical-lr;
}
</style>