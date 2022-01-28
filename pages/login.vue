<template>
    <section>
        <div v-if="$route.query.message" class="alert alert-danger mb-3">
            Need login first
        </div>
        <form @submit.prevent="onSudmit">
            <h1>Login Page</h1>
            <div class="form-group">
                <input type="text" class="form-control">
            </div>

            <p>
                <nuxt-link to="/">To Home Page</nuxt-link>
            </p>

            <button class="btn btn-primary" type="submit">Login</button>

        </form>
    </section>
</template>

<script>
export default {
    layout: 'empty',
    methods: {
        onSudmit() {
            this.$store.dispatch('login'),
            // редирект на главную страницу
            this.$router.push('/')
        }
    }
}
</script>  


<style scoped>
form {
    width: 500px;
    margin: 0 auto;
}

</style>