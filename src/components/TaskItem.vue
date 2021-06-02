<template>
    <div>
        <button @click.self="$emit('complete')" type="button">{{ task.title }}</button>
        <button @click="$emit('remove')" type="button">x</button>
    </div>
</template>

<script>
    export default {
        name: 'TaskItem',
        props: ['task'],
        computed: {
            // className() {
            //     let classes = ['class_item_toggle'];
            //     if ()
            // }
        },
        data: ()=> ({

        }),
        methods: {

        }
    }
</script>
