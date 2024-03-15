<template>
    <div>
        <v-img max-height="210" max-width="100%"
            src="https://img.freepik.com/free-vector/red-wavy-with-halftone-background_1409-1274.jpg?w=2000">
            <v-row>
                <v-col cols="7" class="pa-4">
                    <v-card-text>
                        <v-card-title>
                            {{ title }}
                        </v-card-title>
                        <v-card-text>
                            <p>
                                {{ descript }}
                            </p>
                        </v-card-text>
                    </v-card-text>
                </v-col>
                <v-col cols="5">
                    <v-card-text class="py-0 px-4">
                        <v-card-actions class="pa-0">
                            <v-card-text></v-card-text>
                            <v-spacer></v-spacer>
                            <v-img max-height="100%" max-width="210"
                                src="https://upload.wikimedia.org/wikipedia/commons/0/0b/Humanoid_robot_and_woman_retrieve_infomation_-_includes_a_visible_typical_error_of_recent_AI_generated_pictures.png" />
                            <v-card-text></v-card-text>
                        </v-card-actions>
                    </v-card-text>
                </v-col>
            </v-row>
        </v-img>
        <v-card-text class="py-0">
            <Menu mode="horizontal" :theme="theme" active-name="1" @on-select="menuPost"
                style="display: flex; justify-content: center;">
                <MenuItem name="data">
                <Icon type="ios-paper" />
                Data
                </MenuItem>
                <MenuItem name="about">
                <Icon type="ios-people" />
                About
                </MenuItem>
                <MenuItem name="4">
                <Icon type="ios-construct" />
                Menu1
                </MenuItem>
                <MenuItem name="5">
                <Icon type="ios-construct" />
                Menu2
                </MenuItem>
            </Menu>
        </v-card-text>
        <v-card-text>
            <v-container>
                <v-row>
                    <v-col cols="4" v-for="index in 10" :key="index">
                        <v-card :outlined="index !== outlinedIndex" max-height="250" @mouseenter="outlinedIndex = index"
                            @mouseleave="outlinedIndex = 0" @click="$router.push('/post/posts')">
                            <v-img src="https://www.bhg.com/thmb/WdwZu5ubbBlD-7RftoaCtmvJeVE=/1983x0/filters:no_upscale():strip_icc()/Chinese-New-Year-735a089a20a54d07ae4d1438a9efdcc1.jpg"
                                max-height="150" max-width="100%" />
                            <v-card-title class="pt-2 pb-0 px-4">
                                Title
                            </v-card-title>
                            <v-card-text class="px-6">
                                {{ truncateText(descript, 95) }}
                                <font-awesome-icon icon="plus-circle" style="color: #cccccc;" />
                            </v-card-text>
                        </v-card>
                    </v-col>
                </v-row>
            </v-container>
        </v-card-text>
    </div>
</template>

<script>
export default {
    name: 'YourComponentName', // You can set your component name here
    data() {
        return {
            outlinedIndex: 0,
            theme: 'light',
            title: 'Post page',
            descript: 'If the provided aspect ratio doesn’t match that of the actual image, the default behavior is to fill as much space as possible, clipping the sides of the image. Enabling the contain prop will prevent this, but will result in empty space at the sides.'
        }
    },
    methods: {
        menuPost(name) {
            console.log('Selected menu item:', name);
        },
        truncateText(text, maxLength) {
            if (text.length <= maxLength) return text;
            return text.substring(0, maxLength) + '...';
        }
    }
}
</script>

<style scoped>
/* Add your custom styles here if needed */
</style>