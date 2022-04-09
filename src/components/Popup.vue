<template>
  <div class="text-center">
    <v-dialog
      v-model="dialog"
      width="500"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="red lighten-2"
          dark
          v-bind="attrs"
          v-on="on"
        >
          Click Me
        </v-btn>
      </template>
           
				<Card/>
     
    </v-dialog>
  </div>
</template>

<script>
import Card from '@/components/Card'
   export default{
        components:{Card},
        data(){
					return{
						dialog:false
					}
				}
	 }
</script>