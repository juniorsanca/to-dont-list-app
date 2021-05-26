<template>
    <div>
        <h1 class="d-grid col-8 mx-auto">Mes tâches</h1>

            <div class="list-group">
                <label class="list-group-item">
                    <input class="form-check-input me-1" type="checkbox" value="">
                    {{info}}
                </label>
            </div>
    </div>
</template>

<script>
    import axios from 'axios'
    import {mapActions, mapGetters} from 'vuex'

    export default {
        name: "Todos",

        data: function() {
            return {
             info: ''
            };
        },

        computed: {
            ...mapGetters({'token': 'auth/token'})
        },

        mounted () {
            const config = {
                headers: {
                    Authorization: `Bearer ${this.token}` ,
                },
            }
            axios
                .get(`http://127.0.0.1:8000/api/todos`,
                    config
                ).then((response)=> {
                const i = response.data
                console.log(i[0].name)
                }
            )
        }
    }
</script>
