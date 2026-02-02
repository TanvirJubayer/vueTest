<template>
    <div>
        <h1>user List</h1>

        <table>
            <tr>
                <th>Id</th>
                <th>Name</th>
                <th>Email</th>
                <th>Action</th>
            </tr>
            <tr v-for="user in users" :key="user.id">
                <td>{{ user.id }}</td>
                <td>{{ user.name }}</td>
                <td>{{ user.email }}</td>
                <td>
                    <button>Edit</button>
                    <button>Delete</button>
                </td>
            </tr>
        </table>
    </div>
</template>


<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios';


const users = ref([]);

const fetchUser=()=>{
axios.get(`http://localhost/Tj_Morning-1290594/Project/Laravel/Coffee-shop/Coffee-shop/public/api/Users`)
.then(res=>{
  console.log(res.data.user);
  users.value = res.data.user;
})
.catch(err=>{
  console.log(err);
})
}
onMounted(()=>{
  fetchUser()
})
</script>

<style scoped>
table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 12px;
}
th, td {
  padding: 8px;
  border: 1px solid #ddd;
  text-align: left;
}
.error {
  color: #b00020;
  margin: 8px 0;
}
button {
  margin-right: 6px;
}
</style>