<template>
        <!-- <div   :class="prueba">
            <img src="https://images.pexels.com/photos/2086620/pexels-photo-2086620.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940" alt="" class="image">
            <div>
            <h2 class="title">este es un titulo</h2>
            <p class="description">esta es una descripcion {{hello1}}</p>
            <input type="" style="display:block">
                        <button>boton</button>
            </div>
        </div> -->
<div class="modal fade" :id="'ide'+hello1.id" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
        <div class="container">
      <div class="modal-header container">
          <img :src="hello1.image" alt="" class="image">
        <h5 class="modal-title" id="exampleModalLabel">{{hello1.title}}</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      </div>
      <div class="modal-body">
    {{hello1.description}}
      </div>
      <div class="modal-footer">
          <div class="flex">
          <input type="text">Your Mail
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Suscribe</button>
        </div>
      </div>
    </div>
  </div>
</div>
</template>


<script>
export default {
    data:{
        prueba:''
    },
created(){
      //  this.alineacion()
    },
    props:['hello1'],   
    
    methods:{
        alineacion(){
           // alert('hello')
            if(this.hello1 == 'cardcontainerCenter'){
                this.prueba = 'cardcontainerCenter'
            }
            else if (this.hello1 == 'cardcontainerLeft'){
                this.prueba = 'cardcontainerLeft'
            }
            else{this.prueba = 'cardcontainerRight'}
        }

} 
}
</script>