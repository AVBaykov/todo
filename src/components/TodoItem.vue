<template>
    <div class="todo-item">
        <p>
            {{todo.title}}
            <button class="del" @click="$emit('del-todo', index)">
                <font-awesome-icon icon="times"/>
            </button>
        </p>
    </div>
</template>

<script>
    export default {
        name: "TodoItem",
        props: ["todo","index"]
    }
</script>

<style scoped>
    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .del {
        color: red;
        border: none;
        cursor: pointer;
        float: right;
    }

</style>