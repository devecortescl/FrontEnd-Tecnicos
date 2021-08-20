<template>
  <div class="about">
    <h1>Gestion de Clientes</h1>

<div class="row d-flex justify-content-center">
    <FormClient class="col-lg-4 card"/>
    <TablaClient class="col-lg-7 card" />


</div>


  </div>
</template>

<script>
import FormClient from '../components/FormClient.vue'
import TablaClient from '../components/TablaClient.vue'

export default {
  name: 'Home',
  components: {
    FormClient,
    TablaClient
  }
}
</script>
