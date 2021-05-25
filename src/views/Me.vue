<template>
  <div>
    <h1 class="d-grid gap-2 col-6 mx-auto">Profil</h1>
    <div v-if="user">
    <!--<pre><code>{{ user }}</code></pre>-->
      <ul class="list-group">
        <ul class="list-group-item">nom : {{user.data.name}}</ul>
        <ul class="list-group-item">email : {{user.data.email}}</ul>
      </ul>
    </div>
    <div v-else="">
      <ul class="list-group">
        <ul class="list-groupe-item">Vous n'êtes pas connecté !.</ul>
      </ul>
    </div>
  </div>
</template>

<script>
    import axios from 'axios'
    import { mapGetters } from "vuex"

    export default {
        name: "Me",
        data() {
            return {};
        },
        computed: {
            ...mapGetters({'user': 'auth/user'})
        }
    }
</script>
