<template>
    <div>
        <h1 class="d-grid col-8 mx-auto">Mes tâches</h1>

            <div class="list-group">
                <label class="list-group-item">
                    <input class="form-check-input me-1" type="checkbox" value="">
                    First checkbox
                </label>
            </div>
    </div>
</template>

<script>
    import axios from 'axios'
    import { mapActions } from 'vuex'

    export default {
        name: "Newtodo",
        data() {
            return {
                form: {}
            };
        },
        methods: {
            ...mapActions({'create': 'todos'})
        }
    }
</script>
