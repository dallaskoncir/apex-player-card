<template>
    <div class="container flex flex-col">
        <header class="self-center text-center mb-4">
            <h1>Live Player Card Generator</h1>
            <p>Fill out form below to generate a live card for your currently selected (in game) legend.</p>
        </header>
        <form class="self-center" @submit="onSubmit">
            <div class="mb-2">
                <label for="username">Username</label>
                <input id="username" v-model="username" class="border rounded" type="text" />
            </div>
            <div class="mb-4">
                <label for="platform">Platform</label>
                <select id="platform" v-model="platform" class="border rounded">
                    <option>PC</option>
                    <option>Playstation</option>
                    <option>Xbox</option>
                </select>
            </div>
            <button type="submit" :disabled="isDisabled" class="border rounded p-2">Submit</button>
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
