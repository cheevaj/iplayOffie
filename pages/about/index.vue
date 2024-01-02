<template>
    <div>
        <v-card-title>
            <h2 class="ml-12">
                ABOUT US
            </h2>
        </v-card-title>
        <v-img max-height="400px"
            src="https://www.wallpapers13.com/wp-content/uploads/2015/12/Sunflower-Background-Image.jpg" />
        <div class="color_background">
            <v-container>
                <v-row>
                    <v-col cols="12" sm="9" md="9" class="pa-0">
                        <v-card flat class="pl-12 rounded-0 pt-4">
                            <v-card-text>
                                <h1>
                                    Advancing the power of facts
                                </h1>
                                <br>
                                <p>
                                    The Associated Press is an independent global news organization dedicated to factual
                                    reporting. Founded in 1846, AP today remains the most trusted source of fast, accurate,
                                    unbiased news in all formats and the essential provider of the technology and services
                                    vital
                                    to the news business.
                                </p>
                            </v-card-text>
                            <v-row>
                                <v-col cols="12" sm="4" md="4">
                                    <v-card-text>
                                        <h1>
                                            Our reach
                                        </h1>
                                        <br>
                                        <p>
                                            Four billion people see AP journalism every day.
                                        </p>
                                    </v-card-text>
                                </v-col>
                                <v-col cols="12" sm="4" md="4">
                                    <v-card-text>
                                        <h1>
                                            Our footprint
                                        </h1>
                                        <br>
                                        <p>
                                            Journalists in nearly 100 countries and in all 50 U.S. states.
                                        </p>
                                    </v-card-text>
                                </v-col>
                                <v-col cols="12" sm="4" md="4">
                                    <v-card-text>
                                        <h1>
                                            Our values
                                            <!-- <v-divider style="background-color: brown;"></v-divider> -->
                                        </h1>
                                        <br>
                                        <p>
                                            Accurate, fact-based, nonpartisan reporting.
                                        </p>
                                    </v-card-text>
                                </v-col>
                            </v-row>
                        </v-card>
                    </v-col>
                    <v-col cols="12" sm="3" md="3" class="pa-0">
                        <v-card flat class="rounded-0 pt-6" style="bottom:70px;background-color: rgb(204, 204, 204);">
                            <v-card-text class="px-8">
                                <h2 class="my-2">
                                    The Associated Press
                                </h2>
                                <h2 class="my2">
                                    <span>
                                        200 Liberty St.
                                    </span>
                                </h2>
                                <h2 class="my-2">
                                    New York, NY 10281
                                </h2>
                                <br>
                                <p>Have a question? Email
                                    <a>info@ap.org </a> for general inquiries.
                                </p>
                                <br>
                                <h2>
                                    Follow us
                                </h2>
                                <br>
                                <v-row align="center" justify="center">
                                    <v-btn-toggle dense group style="background-color: transparent; ">
                                        <v-btn fab small text class="mx-2"
                                            style="background-color: transparent; color: transparent;"
                                            @mouseenter="hover = 'all'" @mouseleave="hover = false">
                                            <v-icon size="35" style="background-color: transparent;"
                                                :style="{ color: hover === 'all' ? 'rgb(255, 51, 0)' : '#000' }">mdi-auto-download</v-icon>
                                        </v-btn>
                                        <v-btn class="mx-2" fab small text
                                            style="background-color: transparent; color: transparent;"
                                            @mouseenter="hover = 'whatsapp'" @mouseleave="hover = false">
                                            <v-icon size="35" style="background-color: transparent;"
                                                :style="{ color: hover === 'whatsapp' ? 'rgb(51, 204, 0)' : '#000' }">mdi-whatsapp</v-icon>
                                        </v-btn>
                                        <v-btn fab small text class="mx-2"
                                            style="background-color: transparent; color: transparent;"
                                            @mouseenter="hover = 'facebook'" @mouseleave="hover = false">
                                            <v-icon size="35" style="background-color: transparent;"
                                                :style="{ color: hover === 'facebook' ? 'rgb(51, 51, 255)' : '#000' }">mdi-facebook</v-icon>
                                        </v-btn>
                                    </v-btn-toggle>
                                </v-row>
                                <br>
                                <a href="">Stay connected with our media team at @AP_CorpComm</a>
                            </v-card-text>
                        </v-card>
                    </v-col>
                </v-row>
            </v-container>
        </div>
        <div>
            <v-container>
                <div>
                    <v-card-title>
                        <h2>Product</h2>
                    </v-card-title>
                </div>
                <v-card-text v-for="(item, index) in item" :key="index" class="text-center py-0">
                    <v-row>
                        <v-col v-if="index % 2 === 0" cols="12" sm="6" md="6" class="text_style py-0">
                            <v-card-text>
                                {{ item.text }}
                            </v-card-text>
                        </v-col>
                        <v-col class="d-flex child-flex " cols="12" sm="6" md="6">
                            <v-card-text class="pa-0 text_style">
                                <v-img max-height="350px" max-width="600px" :src="`${item.image}?image=${index * 5 + 10}`"
                                    :lazy-src="`https://picsum.photos/10/6?image=${index * 5 + 10}`" aspect-ratio="1"
                                    class="grey lighten-2">
                                    <template v-slot:placeholder>
                                        <v-row class="fill-height ma-0" align="center" justify="center">
                                            <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                                        </v-row>
                                    </template>
                                </v-img>
                            </v-card-text>
                        </v-col>
                        <v-col v-if="index % 2 !== 0" cols="12" sm="6" md="6" class="text_style">
                            <v-card-text>
                                {{ item.text }}
                            </v-card-text>
                        </v-col>
                    </v-row>
                </v-card-text>
            </v-container>
        </div>
        <div class="color_background">
            <br>
            <br>
            <v-container>
                    <v-row class="my-0 py-0">
                        <v-col v-for="(item, index) in item" :key="index" cols="12" sm="6" md="4" class="py-0" >
                            <v-card flat style="background-color: rgb(255, 255, 255);" max-height="400px" max-width="100%" >
                                <v-img max-height="200" max-width="100%" :src="item.image" />
                                <v-card-text>
                                    {{ item.text }}
                                </v-card-text>
                            </v-card>
                        </v-col>
                    </v-row>
            </v-container>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            hover: false,
            item: [{
                image: 'https://miro.medium.com/max/2400/0*hDAyhnOx767w5qma.jpg',
                text: 'The Associated Press is an independent global news organization dedicated to factual reporting.Founded in 1846, AP today remains the most trusted source of fast, accurate, unbiased news in all formats and the essential provider of the technology and services vital'
            },
            {
                image: 'https://miro.medium.com/max/2400/0*hDAyhnOx767w5qma.jpg',
                text: 'The Associated Press is an independent global news organization dedicated to factual reporting.Founded in 1846, AP today remains the most trusted source of fast, accurate, unbiased news in all formats and the essential provider of the technology and services vital'
            },
            {
                image: 'https://miro.medium.com/max/2400/0*hDAyhnOx767w5qma.jpg',
                text: 'The Associated Press is an independent global news organization dedicated to factual reporting.Founded in 1846, AP today remains the most trusted source of fast, accurate, unbiased news in all formats and the essential provider of the technology and services vital'
            }
            ]
        };
    },
};
</script>
<style>
.text_style {
    display: flex;
    align-items: center;
    justify-content: center;
}

.color_background {
    background-color: rgb(242, 242, 242);
}
</style>