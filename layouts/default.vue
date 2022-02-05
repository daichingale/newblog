<template>
<div class="main_container">
         <NavBar />
         
        <!-- <el-row class="tac">
        <Sidebar />
          <el-col :span="18"> -->
        <div class="centering">
        <Nuxt/>
        </div>  
          <!-- </el-col>
        </el-row> -->

      <Footer />
    
    </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import Sidebar from '@/components/Sidebar.vue';
import Footer from '~/components/Footer.vue'
export default {
  components:{
    NavBar,
    Sidebar,
    Footer,
  }
}
</script>

<style>
.main_container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
.centering{
  margin-left: auto;
  margin-right: auto;
  width: 80%;
}
</style>