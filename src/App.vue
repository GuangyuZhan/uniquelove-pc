<template>
  <div id="app">
    {{info}}
    <!-- <router-view/> -->
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'App',
  data(){
    return{
      info:null,
      jwsr:null
    }
  },
  mounted(){
    axios
      .get('/api/news/wap/fymap2020_data.d.json')
      .then(res=>{
        this.info=res.data.data,
        this.jwsr=res.data.data.jwsrTop
        })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}

</style>
