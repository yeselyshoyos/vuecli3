<template>
    
    <div class="container">
        <h4>Usuarios</h4>
        <input type="text" class="form-control mt-3" v-model="id" placeholder="ID">
        <input type="text" class="form-control mt-3" v-model="name" placeholder="Nombre">
        <input type="text" class="form-control mt-3" v-model="username" placeholder="Nombre de Usuario">
        <input type="text" class="form-control mt-3" v-model="email" placeholder="Correo Electrónico">
        <button class="btn btn-success mt-3" @click="add">Agregar</button>
        <hr>
        <table class="table table-success table-striped rounded">
            <thead>
                <tr>
                    <th scope="col">ID</th>
                    <th scope="col">NOMBRE</th>
                    <th scope="col">NOMBRE DE USUARIO</th>
                    <th scope="col">CORREO ELECTRONICO</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="user in data" :key="user">
                    <th> {{user.id}} </th>
                    <td> {{user.name}} </td>
                    <td> {{user.username}} </td>
                    <td> {{user.email}} </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
import {ref} from 'vue';
import axios from 'axios';
export default {
    name: 'Users',

    setup(){
        let data = ref([]);
        let id = ref(""); 
        let name = ref("");
        let username = ref("");
        let email = ref("");


        const list = () => {

            //data.value = ['Manzana', 'Pera', 'Uva'];
            axios.get("https://jsonplaceholder.typicode.com/users")
            .then((response =>{
                data.value = response.data;
            }));

        }

        const add = () => {
            if(id.value == "" || name.value == "" || username.value  == "" || email.value == ""){
                window.Swal.fire({
                    icon: 'error',
                    title: 'Campos vacios',
                    showConfirmButton: false,
                    timer: 1500
                    })
            }else{
             data.value.push({
                 id: id.value,
                 name: name.value,
                 username: username.value, 
                 email: email.value
             });
                id.value  = "";
                name.value = "";
                username.value  = "";
                email.value = "";

            window.Swal.fire({
                position: 'top-end',
                icon: 'success',
                title: 'Registro exitoso!',
                showConfirmButton: false,
                timer: 1500
                });
            }
        } 
        list();
        return {data, add, id, name, email, username}
    },
}
</script>