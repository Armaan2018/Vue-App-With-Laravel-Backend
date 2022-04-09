<template>
 <v-container>
       <v-card align="left" class="pa-3">
   <v-row>
     <v-col>
   
        <v-img src="logo.png" height="" width="100"></v-img>
        <span class="font-weight-medium dark--text">Add New Product</span>
      
      </v-col>
   </v-row>

<form @submit.prevent="submitForm">
    <v-col sm="12" lg="6">
      <v-text-field label="Product Name" v-model="form.name" outlined class="pa-1" ></v-text-field>
    </v-col>    
    <v-col sm="12" lg="6">
      <v-text-field label="Product Code" v-model="form.code" outlined class="pa-1"></v-text-field>
    </v-col>    
    <v-col sm="12" lg="6">
        <v-select
           v-model="form.category"
          :items="cats"
          label="Select Category"
          outlined
          class="pa-1"
        ></v-select>
    </v-col>
     <v-col sm="12" lg="6">
      <v-text-field label="Product Price" v-model="form.price" outlined  class="pa-1"></v-text-field>
    </v-col>

    <v-col sm="12" lg="6">
  <v-file-input
  class="pa-1"
    label="Upload Product Image"
    outlined
    dense
  ></v-file-input>
    </v-col> 


    <v-col sm="12" lg="6">
        <v-textarea
        v-model="form.description"
          label="Product Short description"
          auto-grow
          outlined
          rows="3"
          row-height="35"
        ></v-textarea>
    </v-col>   


     <v-col sm="12" lg="6" align="right">
          <v-btn :loading="loading"
          type="submit"
      color="blue-grey"
      class="green accent-3 ma-2 white--text"
      

  
    >
      Upload Product
      <v-icon
        right
        dark
      >
        mdi-cloud-upload
      </v-icon>
    </v-btn>
    </v-col>

          <v-snackbar v-model="snackbar" :timeout="4000" top color="info">
            <span class="mx-5">Product Added Successfull</span>
            <v-btn @click="snackbar=false">close</v-btn>
        </v-snackbar>
     
</form> 
      
                
    

   
   </v-row>
     </v-card>
 </v-container>
</template>

<script>
import axios from 'axios';

export default {
  data() {

    return {
      cats:['kamiz','salwar','hizab'],
      form: {
        name:"",
        description:"",
        code:"",
        price:"",
        category:""
      },
      errors: [],
      loading:false,
      snackbar:false,
    }
  },

     methods:{
        submitForm(){
          this.loading = true
            axios.post('http://127.0.0.1:8000/api/store', this.form)
                 .then((res) => {
                     this.form.name = "";
                     this.form.description = "";
                     this.form.code = "";
                     this.form.price = "";
                     this.form.category = "";
                     this.loading = false;
                     this.snackbar = true;
                     // this.$emit('productAdded');


               
             
                 })
                 .catch((error) => {
                     // error.response.status Check status code
                 }).finally(() => {
                     //Perform action in always
                 });
        }
    }
}
</script>