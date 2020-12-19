<template>
    <form @submit.prevent="addTodo()">
<input v-model="newTodo" placeholder="enter the todo" type="text"/>
    </form>
</template>
<script>
export default {
    data(){
        return{
            newTodo:""
        };
    },
    methods: {
        addTodo(){
            if (this.newTodo.length > 1) {
                this.$emit("on-addtodo", this.newTodo)
            }
            this.newTodo = "";
        }
    }
}
</script>
<style>

</style>