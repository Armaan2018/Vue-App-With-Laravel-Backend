<template>
  <v-app>
<MenuHead/>

    <v-content class="mx-4 mb-4 my-4">
      <router-view>
      </router-view>
    </v-content>
  </v-app>
</template>

<script>

import Navbar from '@/components/Navbar'
import TestNav from '@/components/TestNav'
import MenuHead from '@/components/MenuHead'

export default {
  name: 'App',
	components:{Navbar,TestNav,MenuHead},

  data: () => ({
    //
  }),
};
</script>
