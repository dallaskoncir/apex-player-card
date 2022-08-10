<template>
    <PlayerCardFront :username='username' :player-data='playerData.global' :legend-data='playerData.legends?.selected' />
</template>

<script>
    export default {
        data() {
            return {
                username: this.$route.params.username,
                platform: this.$route.params.platform,
                playerData: {}
            }
        },
        async mounted() {
            // Send username and platform to API to get player statistics data
            const { data } = await this.$axios.get(`https://api.mozambiquehe.re/bridge?auth=1bfc0ae82a9ab91df77bab1d62b15e7a&player=${this.username}&platform=${this.platform}`);

            this.playerData = data;
        }
    }
</script>
