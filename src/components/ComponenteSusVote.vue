<template>

<div>
        <div class="container cardcontainerRight">
            <img :src="datos.image" alt="" class="image">
            <div>
            <h2 class="title">{{datos.title}}</h2>
            <p class="description">{{datos.description}}</p>
            <button type="button" class="btn btn-primary forSus" data-toggle="modal" :data-target="'#ide'+datos.id">
                            <p style="display:inline">Suscribe</p>
                            <p style="display:inline; position: relative; left: 150px;">></p>
             </button>
 
            <ComponenteGiveMail :hello1="datos"></ComponenteGiveMail>
</div>
</div>
</div>

</template>


<script>
import ComponenteGiveMail from '@/components/ComponenteGiveMail.vue'

export default {
 components: {
    ComponenteGiveMail,
  },
    props:['datos']
    
}
</script>