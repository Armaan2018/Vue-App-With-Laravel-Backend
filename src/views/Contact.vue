<template>
  <div>
    <ul >
      <li v-for="product in products" :key="product.id">
        <p>{{product.id}}</p>
        <p>{{product.name}}</p>
        <p>{{product.description}}</p>
        <p>{{product.category}}</p>
      </li>
    </ul>

   
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      products: [],
      errors: []
    }
  },

  // Fetches posts when the component is created.
  created() {
    axios.get(`http://127.0.0.1:8000/api/allproducts`)
    .then(response => {
      // JSON responses are automatically parsed.
      // console.log(response.data.product);
      // die;
      this.products = response.data.product
    })
    .catch(e => {
      this.errors.push(e)
    })
  }
}
</script>