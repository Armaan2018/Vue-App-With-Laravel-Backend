<template>
<nav>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title class="text-uppercase grey--text">
				<span class="font-weight-light">Ar</span>
				<span>maan</span>
			</v-toolbar-title>
				<v-spacer></v-spacer>
				<v-btn text color="grey">
				<span>Sign Out</span>
				<v-icon>exit_to_app</v-icon>
			</v-btn>
    </v-app-bar>

    <!-- <v-navigation-drawer v-model="drawer">
      <v-list v-for="link in links" :key="link.text" router :to="link.route">
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item >
            <v-list-item-icon>
              <v-icon>{{link.icon}}</v-icon>
            </v-list-item-icon>
            <v-list-item-title>{{link.text}}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer> -->

			<v-navigation-drawer app v-model="drawer" class="red" >
       <v-list v-for="link in links" :key="link.text" router :to="link.route">
				         <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item >
            <v-list-item-icon>
              <v-icon>{{link.icon}}</v-icon>
            </v-list-item-icon>
            <v-list-item-title>{{link.text}}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
			 </v-list>
		</v-navigation-drawer>
 
</nav>
</template>
<script>
  export default {
    data: () => ({
      drawer: false,
			group:null,
      	links:[
				{icon:'dashboard',text:'Dashboard',route:'/'},
				{icon:'folder',text:'My Projects',route:'/about'},
				{icon:'person',text:'Team',route:'/contact'},
			]
    }),
  }
</script>