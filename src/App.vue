<template>
    <div id="app">
        <TasksList :tasks="tasks"></TasksList>
<!--        <TaskItem v-for="item in tasksList" :key="item" @remove="removeTask"></TaskItem>-->
    </div>
</template>

<script>
    import TasksList from './components/TasksList.vue'
    // import TaskItem from './components/TaskItem.vue'

    export default {
        name: 'App',
        components: {
            TasksList
            // TaskItem
        },
        data: () => ({
            // tasksList: []
        }),
        methods: {
            // removeTask: (e)=> {
            //     console.log(e);
            //     console.log(6);
            // }
        }
    }
</script>
