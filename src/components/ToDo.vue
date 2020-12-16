<template>
    <div class="container">
        <h1>To Do List</h1>
        <input  class="input" v-model="newToDo"/>
        <button class="add-button" @click="add()">Add</button>
        <ul>
            <li v-for="(todo,i) in existingToDo" :key="i">
                <span>
                    {{i + 1}}: {{todo.text}}
                </span>
                <button class="delete-button" @click="deleteToDo(i)"> Delete</button>
            </li>
        </ul>
    </div>
</template>



<script>
export default {
    name: 'vue-to-do',
    data(){
        return{
            newToDo: '',
            existingToDo:[
                {text: 'go for shopping', id: 0},
                {text: 'make cake', id: 1},
                {text: 'cleaning', id: 2}
            ]
        }
    },
    methods:{
        add(){
            this.existingToDo.push({
                text: this.newToDo,
                id: new Date().valueOf()
            }),
            this.newToDo = ''
        },
        deleteToDo(i){
            this.existingToDo.splice(i, 1)
        }
    }
    
}
</script>


<style scoped>
ul{
    list-style-type: none;
}

</style>