<template>
    <div class="todo_wrap">
        <TodoHeaderEj/>
        <TodoInputEj/>
        <div class="list_note">
            <TodoListEj/>
            <TodoFooterEj/>
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
        TodoInputEj,
        TodoListEj,
        TodoFooterEj
    }
}
</script>

<style>
    @import url('https://pro.fontawesome.com/releases/v5.10.0/css/all.css');
    @import url('https://fonts.googleapis.com/css2?family=Itim&display=swap');

    html, body {
        font-family: 'Itim', cursive;
    }
    #app {
        font-family: 'Itim', cursive;
    }

    .todo_wrap {
        padding:200px 0 200px;
        text-align:center;
        background:#f6f6f6;
    }

    button {
        border-style:groove;
    }

    .shadow {
        box-shadow: 5px 10px 10px rgba(0,0,0,0.03);
    }
    .list_note {
        background:#FFF;
        border:2px dashed #eb9a9a;
        padding:20px 10px 0;
        margin:18px;
        height:62vh;

        position:relative;
    }
</style>