<template>
    <div class="container sm mx-auto px-8 max-w-xl h-screen flex flex-col justify-center">
        <h2 class="text-3xl font-semibold text-center">{{ playerData.name }}</h2>
        <img :src='legendData.ImgAssets?.icon' />
        <h3 class="text-2xl font-semibold -rotate-[10deg] text-center">{{ legendData.LegendName }}</h3>
    </div>
</template>

<script>
export default {
    name: 'PlayerCardFront',
    props: {
        username: {
            type: String,
            default: ''
        },
        playerData: {
            type: Object,
            default() {
                return {}
            }
        },  
        legendData: {
            type: Object,
            default() {
                return {}
            }
        }
    }
}
</script>
