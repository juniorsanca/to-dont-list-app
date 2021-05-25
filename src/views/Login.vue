<template>
  <div>
      <h1 class="d-grid gap-2 col-6 mx-auto">Connexion</h1>

    <form @submit.prevent="login(form)">
        <div class="mb-3">
            <label for="email" class="form-label">Email</label>
            <input placeholder="junior@webstart.com" type="email" class="form-control" id="email" name="email" v-model="form.email">
        </div>

        <div class="mb-3">
            <label for="password" class="form-label">Password</label>
            <input type="password" class="form-control" id="password" name="password" v-model="form.password">
        </div>
        <button type="submit" class="btn btn-info d-grid gap-2 col-6 mx-auto" style="color: white">SE CONNECTER</button>
    </form>
  </div>
</template>

<script>
    import { mapActions } from "vuex"

    export default {
        name: "Login",
        data() {
            return {
                form: {}
            };
        },
        methods: {
            ...mapActions({'login': 'auth/login'})
        } 
    }
</script>
