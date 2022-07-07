<template>
    <form @submit="onSubmit">
        <div>
            <label for="username">Username</label>
            <input id="username" v-model="username" type="text" />
        </div>
        <div>
            <label for="platform">Platform</label>
            <select id="platform" v-model="platform">
                <option>PC</option>
                <option>Playstation</option>
                <option>Xbox</option>
            </select>
        </div>
        <button type="submit" :disabled="isDisabled">Submit</button>
    </form>
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
