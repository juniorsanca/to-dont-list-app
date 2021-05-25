<template>
  <div>
    <h1 class="d-grid gap-2 col-6 mx-auto">Inscription</h1>

      <form  @submit.prevent="register(form)">
          <div class="mb-3">
              <label for="name" class="form-label">Name</label>
              <input placeholder="Junior" type="text" class="form-control" id="name" name="name" v-model="form.name">
          </div>

          <div class="mb-3">
              <label for="email" class="form-label">Email</label>
              <input placeholder="junior@webstart.com" type="email" class="form-control" id="email" name="email" v-model="form.email">
          </div>

          <div class="mb-3">
              <label for="password" class="form-label">Password</label>
              <input type="password" class="form-control" id="password" name="password" v-model="form.password">
          </div>

          <button type="submit" class="btn btn-info d-grid gap-2 col-6 mx-auto" style="color: white">S'INSCRIRE</button>
      </form>
  </div>
</template>

<script>
    import axios from 'axios'
    import { mapActions } from 'vuex'

    export default {
        name: "Register",
        data() {
            return {
                form: {}
            };
        },
        methods: {
              ...mapActions({'register': 'auth/register'})
        } 
    }
</script>
