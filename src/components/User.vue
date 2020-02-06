<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>

        {{sex}} {{firstName}} 

             
        
        <hr>
        <div class="row">
            <button @click="changeName">Change name</button>
            <div class="col-xs-12 col-sm-6">
               <app-user-detail @nameWasReset="age=$event" :newAge="ageChanged" :sex="sex" @myFirstName="firstName=$event"></app-user-detail >
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit :age="age" @ageEdited="age=$event"></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';

    export default {
        props:['age', 'firstName'],
        data() {
          return {
            name:'Chika',
            sex: 'female',
          }
        },
        computed:{
          ageChanged(){
            return this.age
          }
        },
        methods:{
          changeName(){
            //alert('hi')
            
            this.name="Anna"
            
          },
          resetName(){
            this.name='max'
          }
        },

        components: {
            appUserDetail: UserDetail,
            appUserEdit: UserEdit
        }
    }
</script>

<style>
    div {
        background-color: lightblue;
    }
</style>
