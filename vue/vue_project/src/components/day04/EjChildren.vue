<template>
    <div class="check_wrap">
        {{ event }}
        <button @click="sendMsg">사전신청</button> 
        <!-- 클릭시 sendMsg 함수 실행 -->
    </div>
</template>

<script>
export default {
    props:['event'],
    methods:{
        sendMsg(){
            this.$emit('sendMsg','마감되었습니다.'); //부모 컴포넌트에 보낼 함수명, 보내고 싶은 데이터
        }
    }
}
</script>

<style lang="scss" scoped>
    .check_wrap {
        margin: 200px auto 80px;
        font-weight: bold;
        
        button {
            background: #333;
            margin-left: 20px;
            border-radius: 15px;
            padding: 12px 20px;
            color: #fff;
            font-weight: normal;
        }
    }
</style>