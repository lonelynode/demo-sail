<template>
  <!-- App -->
  <f7-app :params="f7params">


    <!-- Main View -->
    <f7-view id="main-view" url="/" main></f7-view>



  </f7-app>
</template>

<script>
// Import Routes
import routes from './routes.js'
import './css/app.css'

export default {
  data() {
    return {
      // Framework7 parameters here
      f7params: {
        id: 'io.framework7.testapp', // App bundle ID
        name: 'Framework7', // App name
        theme: 'ios', // Automatic theme detection
        // App routes
        routes: routes,
      },
    }
  },
  mounted: function() {
    // this.$f7.utils.colorThemeCSSProperties('#f00')
  },
}
</script>

<style scoped>
  #main-view .navbar {
    background: white;
  }

  #main-view .navbar-theme {
    background: white;
  }


</style>
