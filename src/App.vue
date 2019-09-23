<template>
  <div id="app">
    <div id="nav">
          <Header1 :tags1="tags" style="margin-bottom:50px"></Header1>
              <router-view/>
    </div>
    <Footer1></Footer1>

  </div>

</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>


<script>
import Header1 from '@/components/Header1.vue'
import Footer1 from '@/components/Footer1.vue'
import axios from 'axios'

export default {
   data(){
        return {
            tags:'',
        }
    },
  components: {
    Header1,
    Footer1
  },
  created(){

    this.getTags()
  },



methods:{
    getTags(){
      const url = process.env.VUE_APP_TAGS
      axios.get(url)
      .then(response => {
        this.tags = response
      })
      .catch(() => {
        alert('error')
      })
    },


}
  
}
</script>