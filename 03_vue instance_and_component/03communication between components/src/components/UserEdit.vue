<template>
    <div class="component">
        <h3>Edit the User here</h3>
        <p>Edit me!</p>
        <p>User Age: {{userAge}}</p>
        <button @click="editAge">Edit Age</button>
    </div>
</template>

<script>
import { eventBus } from '../main';

export default {
    props:['userAge'], 
    methods:{
        editAge(){
            this.userAge = 30;
            //this.$emit('ageWasEdited',this.userAge);

            //1 easy way to emit changes
            //eventBus.$emit('ageWasEdited',this.userAge);

            //other way to emit changes
            eventBus.changeAge(this.userAge);
        }
    }
}
</script>

<style>
    div{
        background: lightgreen;
    }
</style>
