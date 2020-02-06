<template>
    <div class="component">

      

        <h3>You may view the User Details here</h3>       
        
        <p>Many Details</p>
        <p>User name: {{name}}</p>

        <!-- <button @click="resetName()">Reset</button> -->
        
        <button @click="reset">Reset</button>
       <!-- {{newAge}}-->

       {{sex}} {{firstName}}

                
    </div>
</template>

<script>
  import {eventBus} from '../main';
  export default {
    
    data(){
      return {
        age:57,
        firstName: 'Timothy',
      }
    },

    props: ['name', 'resetName', 'newAge', 'sex'] , 

    created(){
      eventBus.$on('ageEdited', (data) => {
        this.newAge = data
      })
    },

    methods:{
      create(){
        window.addEventListener('load',this.emitFirstName)
      },
      reset(){
        //alert('hi')
        //this.name="Max";
        this.$emit('nameWasReset', this.age);
        
      },

      emitFirstName() {
        this.$emit('myFirstName', this.firstName)
      }
      
    }
  }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
