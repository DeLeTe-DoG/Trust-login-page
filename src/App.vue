<template>
  <div className="all">

  <LoginPage v-if="!autorized" />
  <StatisticsPage v-if="autorized" />

  </div>
</template>

<script>
import LoginPage from './components/Login-page/LoginPage.vue';
import StatisticsPage from './components/Statisctics-page/StatisticsPage.vue'
import backgroundScndImg from './assets/images/backgroundScnd.png'

  let autorized = true;


  if (autorized) {
    document.body.style.background = `url(${backgroundScndImg}) no-repeat fixed center`
    document.body.style.backgroundSize = '100%'
  }

  export default {
    components: {LoginPage, StatisticsPage},
    data() {
      return{
        autorized: autorized,
      }
    }
  }
</script>

<style scoped>

</style>