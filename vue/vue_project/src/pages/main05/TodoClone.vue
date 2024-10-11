<template>
    <div class="todo">
        <div class="todo_whole">
            <TodoHeaderEj/>
            <TodoInputEj
            v-on:addTodo="addTodo"
            />
            <TodoListEj
            v-bind:propsdata="todoItems"
            v-on:removeTodo="removeTodo"
            />
            <TodoFooterEj
            v-on:removeAll="clearAll"
            />
        </div>
    </div>
</template>

<script>
import TodoHeaderEj from '../../components/clone/TodoHeadderEj.vue'
import TodoInputEj from '../../components/clone/TodoInputEj.vue'
import TodoListEj from '../../components/clone/TodoListEj.vue'
import TodoFooterEj from '../../components/clone/TodoFooterEj.vue'

export default {
    components:{
        TodoHeaderEj,
        TodoListEj,
        TodoInputEj,
        TodoFooterEj
    },

    data() {
        return {
            todoItems: []
        };
    },
    
    methods: {
        clearAll() {
            localStorage.clear();
            this.todoItems = [];
        },
        addTodo(todoItem) {
            localStorage.setItem(todoItem, todoItem);
            this.todoItems.push(todoItem);
        },
        removeTodo(todoItem, index) {
            localStorage.removeItem(todoItem);
            this.todoItems.splice(index, 1);
        }
    },

    created() {
        if (localStorage.length > 0) {
            for (var i = 0; i < localStorage.length; i++) {
                this.todoItems.push(localStorage.key(i));
            }
        }
    },
}
</script>

<style>
    @import url('https://pro.fontawesome.com/releases/v5.10.0/css/all.css');
    @import url('https://fonts.googleapis.com/css2?family=Itim&display=swap');
</style>

<style lang="scss">
    html, body {
        font-family: 'Itim', cursive;
    }
    #app {
        font-family: 'Itim', cursive;
    }

    .todo {
        width:100%;
        padding:150px 25px;
        background:#f3f3f3;
        &_whole {
            max-width:768px;
            margin:0 auto;
        }
    }
</style>