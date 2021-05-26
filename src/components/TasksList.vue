<template>
    <div>
        <input type="text" placeholder="Название задачи" v-model="newTask">
        <button v-if="newTask !== ''" type="button" @click="newTask = ''">x</button>
        <button type="button" @click="addTask">+ Добавить</button>
        <div v-if="tasksList.length > 0">
            <div v-for="item in tasksList" :key="item" @remove="removeTask(item)">
                <span>{{ item }}</span>
                <button @click="$emit('remove')" type="button">x</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'TasksList',
        data: ()=> ({
            newTask: '',
            tasksList: []
        }),
        methods: {
            addTask() {
                this.tasksList.push(this.newTask);
                return console.log(this.tasksList);
            },
            removeTask(item) {
                this.tasksList.slice(item, 1);
            }
        }
    }
</script>
