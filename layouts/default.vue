<template>
  <v-app>
    <div class="fill-height">
      <v-card absolute color="#ff0000" elevate-on-scroll scroll-target="#scrolling-techniques-7" class="rounded-0"
        style="height: 75px; padding: 0%;">
        <v-row>
          <v-col cols="5" class="color_with pa-0" style="height:75px; clip-path: polygon(0 0, 70% 0, 100% 100% , 0 100%);">

            <v-card-text class="pa-0">
              <v-btn text style="height: 75px; width: 100%; border-top-right-radius: 100%; color:transparent; padding-right: 30%;" @click="$router.push('/')">
                <v-img max-height="75px" max-width="75px"
                  src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e1/Logo_of_YouTube_%282015-2017%29.svg/2560px-Logo_of_YouTube_%282015-2017%29.svg.png" />
              </v-btn>
            </v-card-text>
          </v-col>
          <v-col cols="7" style="height:100%;">
            <v-card-text class="pa-0 pt-1">
              <Menu mode="horizontal" :theme="theme" active-name="1" @on-select="menuSelect" class="colo_red color"
                style="display: flex; justify-content: right;">
                <MenuItem name="../data" style="color: #fff;">
                <Icon class="color_w" type="ios-paper" />
                Data
                </MenuItem>
                <MenuItem name="../about" style="color: #fff;">
                <Icon type="ios-people" />
                About
                </MenuItem>
                <Submenu name="3" style="color: #fff;">
                  <template #title>
                    <Icon type="ios-stats" />
                    Menu
                  </template>
                  <MenuGroup title="Menu">
                    <MenuItem name="../post">Menu</MenuItem>
                    <MenuItem name="">Menu</MenuItem>
                    <MenuItem name="3-3">Menu</MenuItem>
                  </MenuGroup>
                  <MenuGroup title="Menu">
                    <MenuItem name="3-4">Menu</MenuItem>
                    <MenuItem name="3-5">Menu</MenuItem>
                  </MenuGroup>
                </Submenu>
                <MenuItem name="../menu" style="color: #fff;">
                <Icon type="ios-construct" />
                Menu
                </MenuItem>
              </Menu>
            </v-card-text>
          </v-col>
        </v-row>
      </v-card>
      <v-sheet id="scrolling-techniques-7" class="overflow-y-auto">
        <v-main>
          <Nuxt />
        </v-main>
        <v-footer style="background-color: #ff0000;">
          <v-card flat tile class="color_w text-center" style="background-color: #ff0000;">
            <v-card-text style="background-color: #ff0000;">
              <v-btn v-for="(icon, index) in icons" :key="index" class="mx-4 white--text" icon
                @click="openLinkInNewTab(link[index])">
                <v-icon size="24px">
                  {{ icon }}
                </v-icon>
              </v-btn>
            </v-card-text>
            <v-card-text class="white--text px-0 pt-0" style="background-color: #ff0000;">
              Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet. Mauris cursus commodo interdum.
              Praesent
              ut
              risus eget metus luctus accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim a sit amet
              dui.
              Duis commodo vitae velit et faucibus. Morbi vehicula lacinia malesuada. Nulla placerat augue vel ipsum
              ultrices,
              cursus iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum tempor vel ut orci. Orci varius
              natoque
              penatibus et magnis dis parturient montes, nascetur ridiculus mus.
            </v-card-text>
            <v-divider style="background-color: #fff;"></v-divider>
            <v-card-text class="white--text">
              <strong>ITcapital</strong>
            </v-card-text>
          </v-card>
        </v-footer>
      </v-sheet>
    </div>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      theme: 'light',
      icons: [
        'mdi-facebook',
        'mdi-whatsapp',
        'mdi-instagram',
      ],
      link: [
        '', // facebook
        '', // 
        '',
        'https://tplus.la/help',
      ],
    }
  },
  mounted() {
    this.setSheetHeight();
    window.addEventListener('resize', this.setSheetHeight);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.setSheetHeight);
  },
  methods: {
    setSheetHeight() {
      const sheet = document.getElementById('scrolling-techniques-7');
      if (sheet) {
        const screenHeight = window.innerHeight - 65;
        sheet.style.maxHeight = screenHeight + 'px';
      }
    },
    menuSelect(name) {
      // console.log('Selected menu item:', name);
      this.$router.push(name); // Navigate to the "user" page
    },
    openLinkInNewTab(link) {
      window.open(link, '_blank')
    },
  }
}
</script>

<style>
/* Hide scrollbar */
#scrolling-techniques-7::-webkit-scrollbar {
  display: none;
}

/* Fill height utility class */
.fill-height {
  height: 100%;
}

.colo_red {
  background-color: #ff0000;
}

.color_with {
  background-color: #fff;
}

.color_w {
  color: #fff;
}
</style>
