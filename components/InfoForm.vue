<template>
    <div class="container flex flex-col">
        <header class="self-center text-center mb-4">
            <h1 class="text-xl font-semibold mb-2">Live Player Card Generator</h1>
            <p>Fill out form below to generate a live card for your currently selected (in game) legend.</p>
        </header>
        <form class="flex flex-col self-center" @submit="onSubmit">
            <div class="flex items-center mb-2">
                <label for="username" class="mr-2">Username</label>
                <input id="username" v-model="username" class="border rounded px-1.5 py-1" type="text" />
            </div>
            <div class="flex items-center mb-4">
                <label for="platform" class="mr-3.5 basis-1/4">Platform</label>
                <select id="platform" v-model="platform" class="border rounded basis-3/4 px-1.5 py-1">
                    <option>PC</option>
                    <option>Playstation</option>
                    <option>Xbox</option>
                </select>
            </div>
            <button type="submit" :disabled="isDisabled" class="rounded p-2 cursor-pointer text-white font-semibold disabled:bg-red-300 disabled:cursor-default transition ease-in-out delay-75 bg-red-600 hover:bg-red-500 duration-300">Submit</button>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'InfoForm',
        data() {
            return {
                username: '',
                platform: 'PC'
            }
        },
        computed: {
            isDisabled() {
                return !this.username;
            }
        },
        methods: {
            onSubmit(e) {
                e.preventDefault();

                // Route to new view with username/platform, then fetch data on that view from url params
                // url looks like /:username/:platform
                this.$router.push(`/${this.username}/${this.platform}`);
            }
        }
    }
</script>
