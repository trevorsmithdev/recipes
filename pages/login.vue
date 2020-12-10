<template>
    <div class="pt-10">
        <div class="p-10 max-w-sm m-auto shadow-md bg-white">
            <div class="text-2xl text-center mb-10">Log In</div>
            <label>Username</label>
            <input v-model="username" class="block mb-2 w-full" type="text" />
            <label>Password</label>
            <input v-model="password" class="block mb-5 w-full" type="password" />
            <button @click="login" class="w-full">LOG IN</button>
        </div>
    </div>
</template>

<script>
    export default {
        transition: 'fade',
        data() {
            return {
                password: '',
                username: '',
                hasError: true
            }
        },
        methods: {
            async login() {
                const { username, password } = this
                try {
                    const response = await this.$axios.post('/api/login', { username, password })
                } catch (err) {
                    console.error(err)
                }
            }
        }
    }
</script>

<style lang="scss">
    input {
        border: 1px solid black;
    }

    button {
        display: inline-block;
        border-radius: 4px;
        border: 1px solid #3b8070;
        color: #3b8070;
        text-decoration: none;
        padding: 10px 30px;
        background-color: #3b8070;
        color: #ffffff;

        &:hover {
            background-color: #296661;
        }
    }
</style>