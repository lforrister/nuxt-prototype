<template>
    <div>
        <button v-if="!loggedIn" @click="handleLogin">
            Log In 
        </button>
        <button v-else @click="handleLogin">
            Log Out
        </button>
    </div>
</template>

<script>

export default {
    computed: {
        loggedIn() {
            return this.$store.state.login.loggedIn
        }
    },
    methods: {
        handleLogin() {
            let status = this.loggedIn
        
            if (status === true) {
                status = false
            } else {
                status = true 
            }

            this.$store.commit('login/setLoggedIn', status)
        }
    }
}
</script>
