<template>
    <div class="container sm mx-auto px-8 max-w-2xl h-screen flex flex-col justify-center">
        <div class="relative flex flex-col justify-center rounded-md bg-gradient-to-b from-zinc-900 to-zinc-400">
            <header class="relative top-12">
                <h2 class="text-6xl text-slate-200 font-sans font-semibold text-center tracking-wide custom-drop-shadow">{{ playerData.name }}</h2>
            </header>
            <picture class="">
                <img :src="legendData.ImgAssets?.icon" />
            </picture>
            <picture class="absolute bottom-72 right-28">
                <img :src="playerData.rank?.rankImg" />
            </picture>
            <footer class="relative bottom-24 left-2">
                <h3 class="text-9xl uppercase text-red-600 font-sans font-semibold -rotate-[10deg] text-center tracking-wide glowing-text">{{ legendData.LegendName }}</h3>
            </footer>
        </div>
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

<style>
    /* https://css-tricks.com/almanac/properties/t/text-shadow/ */
    .custom-drop-shadow {
        text-shadow: 
            1px 0px 1px #777777, 0px 1px 1px #cccccc, 
            2px 1px 1px #777777, 1px 2px 1px #cccccc,
            3px 2px 1px #777777, 2px 3px 1px #cccccc,
            4px 3px 1px #777777
    }
    /* https://code-boxx.com/glowing-text-pure-css/ */
    .glowing-text {
        text-shadow: 0 0 10px #eeeeee;
    }
</style>
