<template>
<form v-on:submit.prevent="submit" method="post" >
    <div>
        <label>Nombre</label>
        <input type="text" v-model="form.name"/>

        <label>Email</label>
        <input type="text" v-model="form.email"/>

        <label>Phone</label>
        <input type="text" v-model="form.phone"/>

        <label>Location</label>
        <input type="text" v-model="form.location"/>

        <button>Submit</button>
    </div>
</form>
</template>

<script>
import axios from 'axios'

export default {
    data(){
        return {
            form: {
                name: '',
                email: '',
                phone: '',
                location: ''
            }
        }
    },

    methods: {
        submit(){
            axios.post('https://ecortes.cl/test/backend/tecnicos/public/v1/insertClients', this.form)
                .then((response) => {
            console.log(response.data)
            this.cliente = response.data;
            })
        }
    }
}
</script>