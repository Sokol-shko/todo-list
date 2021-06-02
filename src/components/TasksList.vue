<template>
    <div>
        <input type="text" placeholder="Название задачи" v-model="newTask">
        <button v-if="newTask !== ''" type="button" @click="newTask = ''">x</button>
        <button type="button" @click="addTask">+ Добавить</button>
        <div v-if="tasks.length > 0">
            <TaskItem  v-for="(task, index) in tasks" :task="task" :key="task.id" @remove="removeTask(index)" @complete="completeTask(task)"></TaskItem>
        </div>
    </div>
</template>



<script>
    import TaskItem from "./TaskItem";
    export default {
        name: 'TasksList',
        components: { TaskItem },
        props: {
            tasks: { default: [] }
        },
        data: ()=> ({
            newTask: '',
            tasks: []
        }),
        methods: {
            addTask() {
                if (this.newTask) {
                    this.tasks.push({
                        title: this.newTask,
                        completed: false
                    });
                    this.newTask = '';
                }
            },
            completeTask(task) {
                task.completed = ! task.completed;
            },
            removeTask(index) {
                this.tasks.splice(index, 1);
            }
        }
    }
</script>
