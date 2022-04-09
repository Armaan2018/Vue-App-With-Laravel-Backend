<template>
<div>
      <v-snackbar v-model="snackbar" :timeout="4000" top color="info">
    <span class="mx-5">Thats awesome baby</span>
  <v-btn class="black--text" @click="snackbar=false" color="white">Close</v-btn>
  </v-snackbar>
</div>
</template>


<script>
  export default{
    snackbar:true,
  }
</script>