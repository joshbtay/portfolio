<template>
  <ContentPage/>
</template>

<script>
import ContentPage from './components/ContentPage.vue'

export default {
  name: 'App',
  components: {
    ContentPage
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,400;0,600;0,900;1,300&display=swap');
#app {
 font-family: Poppins, Helvetica, Arial, sans-serif;
 -webkit-font-smoothing: antialiased;
 -moz-osx-font-smoothing: grayscale;
 text-align: center;
 display: flex;
 min-height: 100vh;
 flex-direction: column;
}
body::-webkit-scrollbar { 
 display: none;  /* Safari and Chrome */
}
body {
 -ms-overflow-style: none;  /* Internet Explorer 10+ */
 scrollbar-width: none;  /* Firefox */
 margin: 0;
 padding: 0;
}
</style>
