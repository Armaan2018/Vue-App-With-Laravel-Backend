<template>
<v-container
  <v-row>
     <v-col sm="12" md="6" lg="4">
       <v-card
     
       class="mx-auto-my-12"
       max-width="auto">
       <v-img 
       height="250"
       src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
       ></v-img>
       <v-card-title class="green--text">সেই ডিযাইনকে</v-card-title>
       <v-card-text>
         <v-card>
           <v-rating value="4.5" color="amber" dense half-increments readonly size="20" class="pa-5"></v-rating>
           <div class="info--text ms-4">4.5 (126)</div>
           <div class="display-1 pa-5">$ . Italian <span class="font-weight-bold danger--text">Cafe</span></div>
           <div class="caption-text-2 pa-3 font-weight-bold blue--text">Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating </div>
         </v-card>
         <v-divider></v-divider>
   <!--       <Carousel/> -->
    <v-card-text>
      <v-chip-group
        v-model="selection"
        active-class="deep-purple accent-4 white--text"
        column
      >
        <v-chip @click="gadha('5.30')">5:30PM</v-chip>

        <v-chip>7:30PM</v-chip>

        <v-chip>8:00PM</v-chip>

        <v-chip>9:00PM</v-chip>
      </v-chip-group>
    </v-card-text>
     <v-divider></v-divider>
     <v-card>
           <v-card-actions>
      <v-btn
        color="deep-purple lighten-2"
        text
        @click="reserve"
      >
        Reserve
      </v-btn>
    </v-card-actions>
     </v-card>
       </v-card-text>
         
       </v-card>
     </v-col>
  </v-row>
</v-container>
</template>


<script>
import Carousel from '@/components/Carousel'
  export default {
    components:{Carousel},
    data () {
      return {
        forecasts: [
          { text: 'Cash Out', icon: 'home'},
          { text: 'Add Money', icon: 'event'},
          { text: 'Send Money', icon: 'lock'},
          { text: 'Recharge', icon: 'info'},
        ],
      }

    },
    methods:{
      gadha(msg){
         alert(msg)
      }

    }
  }
</script>

<style>
.font-family {
  font-family: 'Mansalva', cursive; 
}
</style>
