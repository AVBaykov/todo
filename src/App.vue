<template>
    <div id="app">
        <Header/>
        <AddTodo v-on:add-todo="addTodo"/>
        <Todos :todos="todos" v-on:del-todo="deleteTodo"/>
    </div>
</template>

<script>
    import Header from './components/layout/Header'
    import Todos from './components/Todos'
    import AddTodo from './components/AddTodo'

    export default {
        name: 'app',
        components: {
            Header,
            Todos,
            AddTodo
        },
        data() {
            return {
                todos: []
            }
        },
        methods: {
            deleteTodo(index) {
                this.todos.splice(index, 1);
            },
            addTodo(newTodo) {
                this.todos.push(newTodo);
            }
        }
    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }

    .btn {
        display: inline-block;
        border: none;
        background: #555;
        color: #fff;
        padding: 7px 20px;
        cursor: pointer;
    }

    .btn:hover {
        background: #666;
    }
</style>
