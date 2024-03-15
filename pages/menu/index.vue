<template>
    <div class="demo-split">
        <v-card outlined class="rounded-0 screen"
            style="width: 100%; position: fixed; height: 100vh; left: 0; overflow: auto; z-index: 100;">
            <!-- <v-card-actions class="pa-0" style="width: 100%; height: 10%;">
                <v-card-text class="text-center pb-0" style="width: 20%; height: 100%;">
                    <h4 style="width: 100%;">Title</h4>
                </v-card-text>
                <v-card-text class="pb-0" style="width: 80%; height: 100%;">
                    <h4 style="width: 100%;">Title</h4>
                </v-card-text>
            </v-card-actions>
            <v-divider /> -->
            <v-card-actions class="pa-0" style="width: 100%; height: 100%;">
                <v-card-text class="pa-0" style="width: 20%; height: 100%;">
                    <div class="layout"
                        style="width: 100%; height: 93%; overflow-y: auto; border-bottom-left-radius: 0; border-bottom-right-radius: 0;">
                        <Menu :theme="theme" :active-name="activeMenuItem" style="width: 100%; height: 100%;">
                            <MenuGroup title="Menu Group">
                                <MenuItem v-for="item in menuItems" :key="item.name" :name="item.name"
                                    @on-click="handleMenuItemClick(item)">
                                <Icon :type="item.iconType" />
                                {{ item.label }}
                                </MenuItem>
                            </MenuGroup>
                        </Menu>
                    </div>
                    <v-card outlined class="text-center pb-0 rounded-0" style="width: 100%; height: 7%;">
                        <h4 style="width: 100%;">Title</h4>
                    </v-card>
                </v-card-text>
                <v-card-text class="py-0" style="width: 80%; height: 100%; overflow-y: auto; ">
                    <service v-if="activeMenuItem === '1'" />
                </v-card-text>
            </v-card-actions>
        </v-card>
    </div>
</template>

<script>
import service from './service.vue';

export default {
    Currency: 'index',
    components: {
        service,
    },
    data() {
        return {
            theme: 'light', // Assuming you have defined theme data
            activeMenuItem: '1', // Initial active menu item
            menuItems: [
                { name: '1', iconType: 'md-document', label: 'Menu 1' },
                { name: '2', iconType: 'md-chatbubbles', label: 'Menu 2' },
                { name: '3', iconType: 'ios-cube-outline', label: 'Menu 3' },
                { name: '4', iconType: 'md-chatbubbles', label: 'Menu 4' },
                { name: '5', iconType: 'md-chatbubbles', label: 'Menu 5' },
            ]
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
            const screen = document.querySelector('.screen');
            if (screen) {
                const screenHeight = window.innerHeight - 64;
                screen.style.height = screenHeight + 'px';
            }
        },
        handleMenuItemClick(item) {
            this.activeMenuItem = item.name;
            console.log('tree', this.activeMenuItem)
        },
    },
};
</script>

<style>
#screen::-webkit-scrollbar {
    display: none;
}

.layout {
    border: 1px solid #d7dde4;
    background: #f5f7f9;
    position: relative;
    border-radius: 4px;
    overflow: hidden;
}

.layout-header-bar {
    background: #fff;
    box-shadow: 0 1px 1px rgba(0, 0, 0, .1);
}

.colo_red {
    color: #ff0000;
}
</style>