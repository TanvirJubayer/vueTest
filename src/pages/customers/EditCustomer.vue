<template>
  <div>
    <h1>Edit Customer</h1>
    <div v-if="loading">Loading...</div>
    <div v-else>
      <form @submit.prevent="handleUpdate">
        <div>
          <label for="name">Name</label>
          <input type="text" id="name" v-model="customer.name" />
        </div>
        <div>
          <label for="email">Email</label>
          <input type="text" id="email" v-model="customer.email" />
        </div>
        <div>
          <label for="phone">Phone</label>
          <input type="text" id="phone" v-model="customer.phone" />
        </div>
        <div>
          <label for="address">Address</label>
          <input type="text" id="address" v-model="customer.address" />
        </div>
        <div>
          <button type="submit">Update</button>
          <button type="button" @click="cancel">Cancel</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup>
import axios from 'axios';
import { reactive, ref, onMounted } from 'vue';
import { useRoute, useRouter } from 'vue-router';

const baseUrl = import.meta.env.VITE_API_BASE_URL;
const route = useRoute();
const router = useRouter();
const id = route.params.id;

const loading = ref(true);
const customer = reactive({
  name: '',
  email: '',
  phone: '',
  address: ''
});

const fetchCustomer = async () => {
  try {
    const res = await axios.get(`${baseUrl}/customers/${id}`);
    // If your API nests the customer inside an object adjust accordingly
    const data = res.data.customer ?? res.data;
    Object.assign(customer, data);
  } catch (err) {
    console.error(err);
  } finally {
    loading.value = false;
  }
};

const handleUpdate = async () => {
  try {
    await axios.put(`${baseUrl}/customers/${id}`, customer);
    router.push('/customers');
  } catch (err) {
    console.error(err);
  }
};

const cancel = () => router.push('/customers');

onMounted(fetchCustomer);
</script>

<style scoped>
/* small spacing */
div > div { margin-bottom: 8px; }
</style>
