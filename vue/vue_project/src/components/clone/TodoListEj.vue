<template>
    <div>
        <ul class="list_wrap">
            <li 
            v-for="todoItem in todoItems" 
            v-bind:key="todoItem"
            class="list_item"
            >
                {{ todoItem }}
                <span 
                class="removeBtn"
                @click="removeTodo(todoItem, index)"
                >
                    <i class="fas fa-trash-alt"></i>
                </span>
            </li>
        </ul>
    </div>
</template>

<script>

export default {
    data() {
        return {
            todoItems: []
        }
    },
    methods: {
        removeTodo: function(todoItem, index) {
            localStorage.removeItem(todoItem);
            this.todoItems.splice(index, 1); // 특정 index에서 하나
        }
    },
    created: function() {
        if (localStorage.length > 0) {
            for (var i = 0; i < localStorage.length; i ++) {
                if (localStorage.key(i) !== 'loglevel:webpack-dev-server') { 
                    this.todoItems.push(localStorage.key(i));
                } // 키에 데이터쓰기
            }
        }
    }
}
</script>

<style lang="scss" scoped>
    .list_wrap {
        list-style:none;
        padding:0;
        margin:20px auto 0;
        text-align:left;
        max-width:340px;
        max-height:46vh;
        overflow:scroll;

        .list_item {
            display:flex;
            min-height:50px;
            height:50px;
            line-height:46px;
            margin:10px 0;
            padding:0 20px;
            background:#FFF;
            border-radius:5px;
            border-bottom:1px dashed #d38787;

            .removeBtn {
                margin-left:auto;
                color:#de4343;
            }
        
        }
    }
</style>