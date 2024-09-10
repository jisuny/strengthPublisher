<template>
    <div class="inputBox shadow">
        <!-- newTodoItem -->
        <input type="text" 
        v-model="TodoItem"
        @:keyup.enter="addTodo"
        >
        <!-- @keyup.enter => 엔터키 사용시에도 리스트 추가 -->

        <span 
        class="addList"
        @click="addTodo"
        >
            <i class="far fa-plus-square addBtn" aria-hidden="true"></i>
        </span>
    </div>
</template>

<script>
export default {
    data () {
        return {
            TodoItem:''
        }
    },
    methods: {
        addTodo: function(){
            console.log(this.TodoItem);
            //v-model 내용 저장
            localStorage.setItem(this.TodoItem, this.TodoItem);
            this.clearInput();
        },
        //초기화
        clearInput: function(){
            this.TodoItem="";
        }
    },
}
</script>

<style lang="scss" scoped>
    .inputBox {
        background:#FFF;
        height:50px;
        line-height:50px;
        border-radius:5px;
        display:flex;
        width:380px;
        margin:0 auto;

        input {
            width:330px;
            outline:none;
            border:1px solid #555;
            font-size:15px;
            padding: 0 20px;
            color:#555;
            font-weight:700;
            text-decoration:underline #f55;
        }

        .addList {
            // background:linear-gradient(45deg, #6462ea, #a7d4fd);

            display:block;
            width: 50px;
            border-radius: 0 5px 5px 0;
            border:1px solid #555;
            font-size: 22px;
            line-height:42px;
            // .addBtn {color:#fff; vertical-align:middle;}
            .addBtn {color:#555; vertical-align:middle;}

        }
    }
</style>