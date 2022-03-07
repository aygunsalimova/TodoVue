<script setup>
import New from './components/New.vue'
</script>

<template>

<div>


<div class="container">
<div class="row">
  <div class="col-6 offset-3 pt-5">
     <form @submit.prevent="add" class="d-flex">
         <input type="text" class="form-control" v-model="value" >
         <button type="submit" class="btn btn-success btn-sm">Add</button>
 </form>

<ul class="list-group mt-5">
  <li class="list-group-item mt-5"  v-for="key, index of arr" :key="key" > 
    
    {{key}}
    
    <button @click="delet(index)" class="btn btn-danger btn-sm">X</button>
    
    </li>
</ul>


  </div>
</div>
</div>

  <New/>
</div>
</template>

<script>
export default {
  data(){
    return{
      value: '',
      arr: [],
      
    }
  },

  methods:{
    add(){

      if(this.value !== ''){
      this.arr.push(this.value);
      this.value="";
      }


    },

    delet(index){
      this.arr.splice(index, 1)
    }
  }
  
}
</script>
