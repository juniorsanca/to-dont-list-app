<template>
    <div>
        <h1 class="d-grid col-8 mx-auto">Ajouter une tâche</h1>

        <form class="addTodo">
            <div class="mb-3">
                <label for="name" class="form-label">Titre</label>
                <input placeholder="title task..." type="text" class="form-control" id="name" name="name" v-model="todo.name">
            </div>

            <div class="mb-3">
                <label for="text" class="form-label">Description</label>
                <input placeholder="your task..." type="text" class="form-control" id="text" name="text" v-model="todo.body">
            </div>

            <button type="submit" @click.prevent="addTodo()" class="btn btn-info d-grid gap-2 col-6 mx-auto" style="color: white">AJOUTER</button>
        </form>
    </div>
</template>

<script>
    import axios from 'axios'
    import { mapActions } from 'vuex'
    import { mapGetters } from 'vuex'

    export default {
        name: "Newtodo",

        data: function() {
            return {
                todo: {
                    name: "",
                    body: "",
                    completed: false
                },
            };
        },

        computed: {
            ...mapGetters({'token': 'auth/token'})
        },
        methods: {
            addTodo() {
                const config = {
                    headers: {
                        Authorization: `Bearer ${this.token}` ,
                    },
                }
                console.log(config)
                axios.post('http://127.0.0.1:8000/api/todos',this.todo,
                    config
                ).then((response)=> (console.log(response.data)))
            },
        }
    }
</script>
