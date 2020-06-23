<template>
    <div>
        <b-form @submit="onSubmit" @reset="onReset" v-if="show">
            <b-form-input
                    id="input-1"
                    v-model="form.email"
                    type="email"
                    required
                    placeholder="email"
            >a</b-form-input>
                <b-button type="submit" variant="primary">Submit</b-button>
            </b-form>

        <b-container>
            <h2 class="mt-5 mb-2">Inscription</h2>
            <b-row >
                <b-col cols="12" md="5" class="m-auto">
                <b-form-input
                        placeholder="Mail"

                >a</b-form-input>
                <b-button type="submit" variant="primary" class="m-3">Submit</b-button>
                </b-col>
            </b-row>
        </b-container>


    </div>
</template>

<script>
    import axios from 'axios';

    export default {
        name: 'contact',
        data() {
            return {
                info: null,
                email: ''
            }
        },

        mounted() {
            axios
                .get('http://apilayer.net/api/check?access_key=10e6e1bc07d743a63a785b8f97624633')
                /*.then(response => (this.info = response))
*/
                .then(response => {
                    // JSON responses are automatically parsed.
                    this.posts = response.email
                })
                .catch(e => {
                    this.errors.push(e)
                })
        }
    }
</script>


