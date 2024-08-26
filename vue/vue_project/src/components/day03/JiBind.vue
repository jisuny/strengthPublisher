<template>
    <h3>ref 를 이용한 네이밍 업데이트</h3>
    <div class="container">
        <div class="name">{{ name }}</div>
        <div>
            <input
            class="name_txt"
            :type="type"
            :placeholder="'텍스트를 입력해 주세요'"
            >
            <button
                @click="nameUpdate"
            >버튼</button>
        </div>
    </div>
</template>

<script>
import { ref } from 'vue'; //vue3 에서 ref는 반응성 데이터로 만들어 줌
export default {
    setup() {
        let name = ref("입력값이 여기에 출력돼요");
        let type = ref("text")

        const nameUpdate = () =>{
            const $nameTxt = document.querySelector('.name_txt').value;
            if($nameTxt == '' || $nameTxt == undefined){
                name.value = '텍스트를 입력해 주세요.'
            } else {
                name.value = $nameTxt;
            }
        }
        return {
            name,
            type,
            nameUpdate
        };
    }
}
</script>
<style lang="scss" scoped>
.container{
    margin:15px 0;
    padding:0 10px;
    >div{
        display: flex;
        justify-content: center;
        gap: 15px;
    }
    .name{
        margin:0 auto 15px;
        padding:0 10px;
        width:100%;
        line-height: 54px;
        font-weight: bold;
        font-size:18px;
        border-radius: 15px;
        background-color:#dac3ff;
        color:#23133b
    }
    input{
        padding:0 10px;
        width:300px;
        height:60px;
        line-height: 54px;
        font-weight: 300;
        font-size:18px;
        border-radius: 15px;
        border:2px solid #dac3ff;
        font-size:15px;
    }
    button{
        width:100px;
        height:60px;
        line-height: 60px;
        font-weight: bold;
        font-size:15px;
        border-radius: 15px;
        background-color:#44198a;
        color:#fff;
    }
}
  
</style>