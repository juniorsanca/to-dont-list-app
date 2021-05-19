<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/register">Register</router-link> |
    <router-link to="/login">Login</router-link> |
    <router-link to="/me">Me</router-link> |
    <a href="#" @click.prevent="logout">Logout</a>
  </div>
  <router-view/>
</template>

<script>
    import axios from 'axios'
    import { mapActions } from "vuex"

    export default {
        methods: {
            ...mapActions({'logout': 'auth/logout'})
        }
    }
</script>
