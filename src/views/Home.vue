<template>
  <div class="home">
 
  <div class="container" style="width:50%">
    <!-- <ComponenteSusVote v-for="datacard in datacards.data" :key="datacard.id" :datos="datacard"></ComponenteSusVote>  -->
  </div>
    <div class="container">
  <div class="row">
    <ComponenteSusVote v-for="datacard in datacards.data" :key="datacard.id" :datos="datacard"></ComponenteSusVote>

    </div>
  </div>
</div>
   

</template>

<script>
// @ is an alias to /src
//import HelloWorld from '@/components/HelloWorld.vue'
import styles from '@/styles.css'
import ComponenteSusVote from '@/components/ComponenteSusVote.vue'
import ComponenteGiveMail from '@/components/ComponenteGiveMail.vue'
import axios from 'axios'

export default {
  data(){
        return {
            prueba: 'cardcontainerRight',
            datacards: '',
            tags:''
        }
    },
  name: 'home',
  created(){
    this.getNews()
    this.getTags()
  },
  components: {
    //HelloWorld
    ComponenteSusVote,
    ComponenteGiveMail,
  },
  methods:{
    getNews(){
      const url = process.env.VUE_APP_NEWS
      axios.get(url)
      .then(response => {
        this.datacards = response
      })
      .catch(() => {
        alert('error')
      })
    },

    getTags(){
      const url = process.env.VUE_APP_TAGS
      axios.get(url)
      .then(response => {
        this.tags = response
      })
      .catch(() => {
        alert('error')
      })
    }
  }
}
</script>
