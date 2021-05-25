<template>
  <div id="nav" class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">To dont list</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <ul class="list-group">
            <ul class="list-group-item"><router-link to="/">Accueil</router-link></ul>
            <ul class="list-group-item"><router-link to="/register">Inscription</router-link></ul>
            <ul class="list-group-item"><router-link to="/login">Connexion</router-link></ul>
            <ul class="list-group-item"><router-link to="/me">Mon profil</router-link></ul>
            <ul class="list-group-item"><router-link to="/addtodos">Ajouter une tâche</router-link></ul>
            <ul class="list-group-item"><router-link to="/todos">Mes tâches</router-link></ul>
            <ul class="list-group-item"><a style="float: right" href="#" @click.prevent="logout">Déconnexion</a></ul>
          </ul>
        </div>
      </div>
    </div>
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
