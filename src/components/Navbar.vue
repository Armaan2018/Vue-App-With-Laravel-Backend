<template>
	<nav>
		<v-app-bar app>
			<v-btn text color="grey" @click="drawer = !drawer">
				<v-icon>menu</v-icon>
			</v-btn>
			<v-toolbar-title class="text-uppercase grey--text">
				<span class="font-weight-light">Todo</span>
				<span>Ninja</span>
			</v-toolbar-title>
			<v-spacer></v-spacer>
			<v-btn text color="grey">
				<span>Sign Out</span>
				<v-icon>exit_to_app</v-icon>
			</v-btn>
		</v-app-bar>

		<v-navigation-drawer app v-model="drawer" class="red" >
       <v-list v-for="link in links" :key="link.text" router :to="link.route">
				 <v-list-tile>
					 <v-list-tile-action>
						 <v-icon class="white--text">{{link.icon}}</v-icon>
					 </v-list-tile-action>
					 <v-list-content>
						 <v-list-tile-title class="white--text">
							 {{link.text}}
						 </v-list-tile-title>
					 </v-list-content>
				 </v-list-tile>
			 </v-list>
		</v-navigation-drawer>
	</nav>
</template>

<script>
  export default {
    data () {
      return {
        drawer: true,
        items: [
          { title: 'Home', icon: 'mdi-home-city' },
          { title: 'My Account', icon: 'mdi-account' },
          { title: 'Users', icon: 'mdi-account-group-outline' },
        ],
        mini: true,
      }
    },
  }
</script>