<template>
    <div>
        <div v-for="(todo, index) in todos">
            <TodoItem :todo="todo" :index="index" v-on:del-todo="$emit('del-todo', index)"/>
        </div>
    </div>
</template>

<script>
    import TodoItem from './TodoItem'

    export default {
        name: "Todos",
        components: {TodoItem},
        comments: {
            TodoItem
        },
        props: ["todos"]
    }
</script>

<style scoped>

</style>