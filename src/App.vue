<script >
import axios from 'axios'
  export default  {
    name: 'App',
    components: {
      Navbar
    },
    beforeCreate(){
      this.$store.commit('initializeStore')

      if(this.$store.state.token){
        axios.defaults.headers.common['Authorization'] = 'Token ' + this.$store.state.token
      } else{
        axios.defaults.headers.common['Authorization'] = ''

      }

    }

  }

import Navbar from './Layout/Navbar.vue'
</script>

<template>
 
  <Navbar />
  <router-view />
</template>

<style>

</style>
