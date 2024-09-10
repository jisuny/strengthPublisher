<template>
    <div 
    class="clearAllContainer"
    >
        <span 
        class="clearAllBtn"
        @click="clearTodo"
        >
        ClearAll
        </span>
    </div>
</template>

<script>
export default {
    methods: {
        clearTodo: function(){
            localStorage.clear(); //모든 키 데이터 삭제
        }
    }  
}
</script>

<style lang="scss" scoped>

.clearAllContainer {
    width:46%;
    margin:100px auto 20px;
    height:50px;line-height:48px;
    background:#FFF;
    border-radius:5px;

    position:absolute;
    bottom:0;left:50%;transform:translateX(-50%);

    .clearAllBtn {
        display:block;
        color:linear-gradient(45deg, #6462ea, #a7d4fd);
        font-weight:bold;
        border-bottom:1px solid #555;
        border-radius:8px;
    }
}

</style>