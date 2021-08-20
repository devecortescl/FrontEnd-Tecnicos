<template>
  <div>
   
   <table class="table table-dark">
  <thead >
    <tr >
      <th scope="col">#</th>
      <th scope="col">Nombre</th>
      <th scope="col">Email</th>
      <th scope="col">Telefono</th>
      <th scope="col">Direccion</th>
    </tr>
  </thead>
  <tbody>
    <tr  v-for="cliente in clientes" :key="cliente.id" >
      <th scope="row">{{cliente.id}}</th>
      <td>{{cliente.name}}</td>
      <td>{{cliente.email}}</td>
      <td>{{cliente.phone}}</td>
      <td>{{cliente.location}}</td>
     
    </tr>

  </tbody>
</table>


  </div>
</template>

<script>
import axios from "axios";
 export default {
name: 'Home',
    data() {
      return {
        clientes:[],
    
        }
  },
methods: {
    
    

    getClients(){ 

          axios.get('https://ecortes.cl/test/backend/tecnicos/public/v1/showClients', 
          {
          'Cache-Control': null, 
          'X-Requested-With': null,},
          ).then((response) => {
            console.log(response.data)
            this.clientes = response.data;
            })


    }
 

    
},
created() {
    this.getClients();
  },
    }

</script>
