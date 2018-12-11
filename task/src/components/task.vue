<template>
  <div class="task">
    <div id="divv">
  <h1> Users List</h1>
  </div>
  <br>
    <table>
    <tr >
       <th>Id</th>
       <th>Name</th>
       <th>U.name</th>
       <th>Email</th>
        <th colspan="6">Address</th>
       <th>Phone</th>
       <th>Website</th>
      <th colspan="3">company</th>


    </tr>
    <tr >
       <th></th>
       <th></th>
       <th></th>
       <th></th>

        <th>street</th>
        <th>suite</th>
        <th>city</th>
        <th>zipcode</th>
        <th>latitude</th>
        <th>lng</th>

       <th></th>
       <th></th>

      <th>name</th>
      <th>catchPhrase</th>
      <th>bs</th>



    </tr>
    <tr v-for="user in users">
      <td>{{user.id}}</td>
      <td>{{user.name}}</td>
      <td>{{user.username}}</td>
      <td>{{user.email}}</td>
        <td>{{user.address.street}}</td>
        <td>{{user.address.suite}}</td>
        <td>{{user.address.city}}</td>
        <td>{{user.address.zipcode}}</td>
        <td>{{user.address.geo.lat}}</td>
        <td>{{user.address.geo.lng}}</td>
      <td>{{user.phone}}</td>
      <td>{{user.website}}</td>
        <td>{{user.company.name}}</td>
        <td>{{user.company.catchPhrase}}</td>
        <td>{{user.company.bs}}</td>

    </tr>
  </table>
  </div>
</template>
<script>
import axios from "axios";

export default {
  name: 'task',
  props: {

  },
  data(){
    return{

        users: []

    }
  },
  mounted(){
        axios.get("https://jsonplaceholder.typicode.com/users")
        .then(response => {this.users = response.data})
  }
}
</script>


<style scoped>
  table {

 border: 2px solid #822a4a;
 width: 0%;
 margin: auto;
 text-align:center;
 box-shadow: 3px 3px #a18f81;

}

th, td {
 text-align: center;
 padding: 10px;

}

tr{ background-color: #fcfedd;}

th {
 background-color: #822a4a;
 color: white;
}

h1{
  font-size:24pt;
  color:#822a4a;
}
#divv{
  background-color:#fcfedd;
  width:35%;
  padding:0.1%;
  margin-left:32%;
  border-radius:20px;
  border-bottom: 5px solid #822a4a;
  box-shadow: 3px 3px #a18f81;
}
</style>
