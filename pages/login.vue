<template>
    <div class="pt-10">
        <div class="p-10 max-w-sm m-auto shadow-md bg-white">
            <div class="text-2xl text-center mb-10">Log In</div>
            <label>Username</label>
            <input v-model="username" class="block mb-2 w-full" type="text" />
            <label>Password</label>
            <input v-model="password" class="block mb-5 w-full" type="password" />
            <button @click="login" class="button--green w-full">LOG IN</button>
        </div>
    </div>
</template>

<script>
    export default {
        transition: 'fade',
        data() {
            return {
                password: '',
                username: ''
            }
        },
        methods: {
            async login() {
                const { username, password } = this
                const response = await this.$axios.post('/api/login', { username, password })
                console.log(response)
            }
        }
    }
</script>

<style>
    input {
        border: 1px solid black;
    }
</style>