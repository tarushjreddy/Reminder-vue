<template>

<div>


<li >
    <button v-if="!isEditing" class="orient">{{todoResult}}</button>

    <form v-else @submit.prevent="endEditing()">
        <input @blur="startEditing()" v-model="newTodoString" type="text">
    </form>

    <button @click="startEditing()" class="edit">Edit</button>
    <button @click="$emit('on-delete')" class="delete">delete</button>
</li>
</div>
</template>

<script>


export default {
      components : {

  },
    props:{
        todoResult: String,
        completed: Boolean
    },
    data(){
        return {
            isEditing: false,
            newTodoString: "",
        };
    },
    methods:{
        startEditing(){
            if (!this.isEditing) {
                    
                this.newTodoString = this.todoResult;
            this.isEditing = true;
            } else{
                this.endEditing();
            }
        },
        endEditing(){
            this.isEditing = false,
            this.$emit('on-edit', this.newTodoString)
        }
    }
};
</script>
<style scoped>
.orient{
    width: 500px;
    height: 50px;

}
input{
    width: 500px;
    height: 50px;
}
button{
    outline: none;

}
li {
    display: flex;
}
.delete, .edit{
    outline: none;
    border: none;
    padding: 20px;
}
.delete:hover {
    background-color: red;
    transition: all 200ms ease-in-out;
    color: white;
}
.edit:hover{
    background-color: rgb(21, 21, 75);
    transition: all 200ms ease-in-out;
    color: white;
}
</style>