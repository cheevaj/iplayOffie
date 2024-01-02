<template>
  <v-app dark>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn icon @click.stop="clipped = !clipped">
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-btn icon @click.stop="fixed = !fixed">
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-toolbar-title>{{ title }}</v-toolbar-title>
      <v-spacer />
      <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <Nuxt />
    </v-main>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light> mdi-repeat </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer dark padless>
      <v-card flat tile class="red lighten-1 text-center" width="100%">
        <v-card-text>
          <v-btn :style="{ backgroundColor: item.backgroundColor }" v-for="item in icons" :key="item.icon"
            class="mx-4 white--text" icon @click="openLinkInNewTab(item.link)">
            <v-icon :color="item.color" size="30px">{{ item.icon }}</v-icon>
          </v-btn>
        </v-card-text>

        <v-card-text class="white--text pt-0">
          Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet. Mauris cursus commodo interdum. Praesent ut
          risus eget metus luctus accumsan id ultrices nunc.
        </v-card-text>
        <v-divider></v-divider>
        <v-card-text class="white--text text-h7">
          <strong><span class="text-h6">Ipay App</span></strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
      ],
      icons: [
        {
          icon: 'mdi-facebook',
          backgroundColor: 'blue',
          title: 'Welcome',
          link: '',
          color: '#fff',
        },
        {
          icon: 'mdi-whatsapp',
          backgroundColor: '#00cc00',
          title: 'Welcome',
          link: '',
          color: '#fff',
        },
        {
          icon: 'mdi-youtube',
          backgroundColor: '#fff',
          title: 'Welcome',
          link: '',
          color: '#e60000',
        },
        {
          icon: 'mdi-instagram',
          backgroundColor: '#ff33cc',
          color: '#fff',
          title: 'Welcome',
          link: '',
        },
      ],
      miniVariant: true,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
    }
  },
}
</script>
