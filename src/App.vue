<template>
  <div id="app">
    <router-view/>
    <FooterHome/>
  </div>
</template>

<script>
import FooterHome from '@/components/FooterHome.vue';

export default {
  components:{
    FooterHome
  } 
  
}
</script>