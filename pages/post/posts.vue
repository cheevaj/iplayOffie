<template>
    <div>
        <v-container>

            <v-card-title class="pb-0">
                <h4>Knowledge & News</h4>
            </v-card-title>
            <v-divider style="background-color: #ff0000; margin-left: 15px; width: 177px; padding-top:2px;"></v-divider>
            <v-divider style="background-color: #ff0000; margin-left: 15px;"></v-divider>
            <v-card-title>
                <h4>
                    {{ title }}
                </h4>
            </v-card-title>
            <v-card-text v-for="i in 3" :key="i">
                <v-img :src="inmage" />
                <v-card-text>
                    <!-- <h4>DESCRIPTS</h4> -->
                    <!-- <v-divider style="background-color: #ff0000;width: 75px; padding-top:1px;"></v-divider> -->
                    <div style="font-size: 16px;">{{ text }}</div>
                </v-card-text>
            </v-card-text>
            <v-card-text>
                <v-card-text class="text-center">
                    <h4 style="font-size: 18px;">{{ title }}</h4>
                </v-card-text>
                <v-divider style="background-color:rgb(230, 230, 230);"></v-divider>
                <br>
                <div class="px-4" style="font-size: 18px;">{{ title }}</div>
                <br>
                <v-divider style="background-color:rgb(230, 230, 230);"></v-divider>
            </v-card-text>
        </v-container>

    </div>
</template>

<script>
export default {
    data() {
        return {
            title: 'Banque Pour Le Commerce Exterieur Lao Public (BCEL) has held seminars on the topic of Anti-Money Laundering and Combating the Financing of Terrorists (AML/CFT)',
            text: 'Lao Banker’s Association (LBA) hosted the 23rd ASEAN Banking Association Conference & 51st ASEAN Banking Council Meeting, under the slogan Digitalisation and Sustainable Growth in Banking Sector of ASEAN: Opportunity and Challenges at the Landmark Mekong RiverSide Hotel in Vientiane Lao PDR from 06 – 08 December 2023.',
            inmage: 'https://www.bcel.com.la/bcel/bcelweb-datas/file-path/image-upload/img/bcel_web_file_87_c1cbdb8613667a0e2961bb4028bd9216.jpg',
        }
    }
}
</script>