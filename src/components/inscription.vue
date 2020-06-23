<template>
    <div>
        <h2>Formulaire d'inscription</h2>
        <b-container>
            <b-col cols="12" md="5" class="m-auto">
        <b-form @submit="onSubmit" @reset="onReset" v-if="show">
            <b-form-group
                    id="input-group-1"
                    label="Email :"
                    label-for="input-1"
            >
                <b-form-input
                        id="input-1"
                        v-model="form.email"
                        type="email"
                        required
                        placeholder="Mail"
                ></b-form-input>
            </b-form-group>

            <b-form-group id="input-group-2" label="Nom :" label-for="input-2">
                <b-form-input
                        id="input-2"
                        v-model="form.name"
                        required
                        placeholder="Nom"
                ></b-form-input>
            </b-form-group>

            <b-button type="submit" variant="primary" class="m-2">Soumettre</b-button>
            <b-button type="reset" variant="danger" class="m-2">Reset</b-button>
        </b-form>
            </b-col>
        </b-container>
    </div>
</template>

<script>

    export default {
        name: "inscription",
        data() {
            return {
                form: {
                    email: '',
                    name: '',
                    food: null,
                    checked: []
                },
                show: true,
                info:null
            }
        },
        methods: {
            onSubmit(evt) {
                evt.preventDefault()
                alert(JSON.stringify(this.form))
            },
            onReset(evt) {
                evt.preventDefault()
                // Reset our form values
                this.form.email = ''
                this.form.name = ''
                this.form.food = null
                this.form.checked = []
                // Trick to reset/clear native browser form validation state
                this.show = false
                this.$nextTick(() => {
                    this.show = true
                })
            },
        }
    }

</script>

<style scoped>

</style>
