<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add Todo...">
            <button type="submit" class="btn">
                <font-awesome-icon icon="plus-circle"/>
            </button>
        </form>
    </div>
</template>

<script>
    export default {
        name: "AddTodo",
        data() {
            return {
                title: ''
            }
        },
        methods: {
            addTodo(e) {
                e.preventDefault();
                const newTodo = {
                    title: this.title
                };
                this.$emit('add-todo', newTodo);
                this.title = '';
            }
        }
    }
</script>

<style scoped>
    form {
        display: flex;
    }

    input[type="text"] {
        flex: 10;
        padding: 5px;
    }

    input[type="submit"] {
        flex: 1;
    }
</style>