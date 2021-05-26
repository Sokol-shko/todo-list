<template>
    <div id="app">
        <TasksList></TasksList>
        <TaskItem></TaskItem>
    </div>
</template>

<script>
    import TasksList from './components/TasksList.vue'
    import TaskItem from './components/TaskItem.vue'

    export default {
        name: 'App',
        components: {
            TasksList,
            TaskItem
        },
        data: () => ({

        })
    }
</script>
