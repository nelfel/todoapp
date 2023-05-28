<template>
    <h1>To Do App{{ fullname }}</h1>
    <input @keyup.enter="addNewTask" ref="txtTask" type="text" v-model="newTask" placeholder="Add space">
    <button @click="addNewTask">Add</button>
    <ul>
        <li v-for="(item, index) in todolist " :key="index">
            {{ item }}
            <button id="btnDelete" @click="removeTask(index)">Delete</button>
        </li>
    </ul>
</template>

<script>

export default {
    name: "TaskComponet",
    data() {
        return {
            todolist: [],
            fullname: "Nelson Acosta",
            newTask:""

        }
    },
    methods: {
        addNewTask() {
            console.log("Aqui se agregara la tarea")
            this.todolist.push(this.newTask)
            this.$refs.txtTask.focus()
        },
        removeTask(index){
            console.log("El valor de index es: " + index)
            this.todolist.splice(index,1)
        }
    }
}

</script>

<style>

button{

    background-color: blue;
    color: whitesmoke;
}

button:hover {
    background-color: yellow;
    color: darkmagenta;

}
#btnDelete{
    background-color: blue;
    color: burlywood;
}
</style>