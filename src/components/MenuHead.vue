<template>
<nav>

	<v-snackbar v-model="snackbar" :timeout="4000" top color="info">
		<span class="mx-5">Thats awesome baby</span>
	<v-btn class="black--text" @click="snackbar=false" color="white">Close</v-btn>
	</v-snackbar>


	<v-app-bar app>
			<v-btn text color="grey" @click="drawer = !drawer">
				<v-icon>menu</v-icon>
			</v-btn>
	</v-app-bar>

	<v-navigation-drawer app v-model="drawer" class="primary" >
      <v-list>
				<v-list-item v-for="link in links" :key="link.text" router :to="link.route" class="mx-2 my-8">
					<v-list-item-action>
						<v-icon class="white--text">{{link.icon}}</v-icon>

					</v-list-item-action>
					<v-list-item-content>
						<v-list-item-title class="white--text">{{link.text}}</v-list-item-title>

					</v-list-item-content>

				</v-list-item>
<Popup/>
			</v-list>
	</v-navigation-drawer>

</nav>
</template>

<script>
import Popup from '@/components/Popup'
export default{
	components:{ Popup },
	data(){
		 return {
        drawer: true,
				group: null,
				
        	links:[
				{icon:'dashboard',text:'Dashboard',route:'/'},
				{icon:'folder',text:'My Projects',route:'/about'},
				{icon:'person',text:'Team',route:'/contact'},
			],
			snackbar:false,
        mini: true,
      }
	}

}
</script>