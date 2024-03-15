<template>
    <div>
        <div v-for="(i,index) in 4" :key="index">
            <br v-if="index !== 0">
            <v-card-title>
                <h2>Usage</h2>
            </v-card-title>
            <v-card-text>
                <p>The v-badge component superscripts or subscripts an avatar-like icon or text onto content to
                    highlight information to a user or to just draw attention to a specific element. Content
                    within the badge usually contains numbers or icons.</p>
            </v-card-text>
            <v-card-actions class="text-center pa-0" style="width: 100%; display: flex; justify-content: center;">
                <v-img max-height="40%" max-width="50%" class="mx-1"
                    src="https://www.storagenewsletter.com/wp-content/uploads/old/icono5/inmage_systems_with_5.1_software_release_540.jpg" />
                <v-img max-height="40%" max-width="50%"
                    src="https://www.storagenewsletter.com/wp-content/uploads/old/icono5/inmage_systems_with_5.1_software_release_540.jpg" />
            </v-card-actions>
        </div>
    </div>
</template>