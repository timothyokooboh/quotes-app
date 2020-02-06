<template>
    <div class="component">

      {{sex}}

        <h3>You may edit the User here</h3>
        <p>Edit me!</p>
        <button @click="editAge">edit age</button>
        {{age}}

    </div>
</template>

<script>

  import {eventBus} from '../main';

  export default{
  props:['age'],

  methods:{
    editAge() {
      this.age = 42; 
      //this.$emit('ageEdited', this.age)
      eventBus.$emit('ageEdited', this.age)
    }
  }
  }
</script>

<style scoped>

    div {
        background-color: lightgreen;
        
    }

</style>
