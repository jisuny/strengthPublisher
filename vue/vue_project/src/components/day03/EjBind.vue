<template>
<div class="binding_wrap">
    <div class="container">
        <h2>V-bind</h2>
        <div class="result name">{{name}}</div>
        <div class="btn_wrap">

            <input type="text" 
            v-bind:value="name"
            >
            
            <button 
            class="btn btn-pri" 
            v-on:click="updateResult"
            >
                Click
            </button>
        </div>
    </div>
    <div class="container">
        <h2>V-bind:type | V-model</h2>
        <div class="result name">{{valueNum}}</div>
        <div class="btn_wrap">

            <input 
            :type="type" 
            v-model="valueNum" 
            placeholder="숫자입력"
            >
        </div>
    </div>

    <div class="container">
        <h2>TextUpdate</h2>
        <div class="result name">{{ nameupdate }}</div>
        <div class="btn_wrap">

            <input type="text" class="name_text">
            
            <button 
            class="btn btn-pri" 
            @click="updatename2"
            >
                Click
            </button>
        </div>
    </div>
    <div class="container">
        <h2>NumUpdate</h2>
        <div class="result num"><strong>{{ numupdate }}</strong>개월에 '<strong>{{50000 * numupdate}}</strong>'원 입니다.</div>
        <div class="btn_wrap">

            <input 
            :type="type"
            class="num_in"
            placeholder="예상 개월 수 입력"
            min="1"
            max="12"
            >
            
            <button 
            class="btn btn-pri" 
            @click="updatenum"
            >
                Click
            </button>
        </div>
    </div>
</div>
</template>

<script>

    import {ref} from 'vue' // ref 변수 값 변동 자동업뎃 ->value속성

    export default {
        name:'EjBind', //  필수지정X, 값 찾아올 때 도움

        data(){
            return {
                valueNum : "0",
            }
        },

//composition API
        setup() { //vue.js3 부터 setup 기능_ 
            let name= ref("input01");
            let type= ref("number");
            let nameupdate = ref("입력값 대기");
            let numupdate = ref("00")

            var updateResult = ()=>{
                name.value="result";
                // type.value="33"
                console.log(name);
            }

            var updatename2 = () =>{
                var nameupdate_con = document.querySelector('.name_text').value;
                if(nameupdate_con == '' || nameupdate_con == undefined){
                    // nameupdate.value = ""
                } else {
                    nameupdate.value = nameupdate_con;
                }
            }

            var updatenum = () =>{
                var num_con = document.querySelector('.num_in').value;
                if(num_con == '' || num_con == undefined){
                    // nameupdate.value = ""
                } else {
                    numupdate.value = num_con;
                }
            }


            return{
                name, updateResult, type, 
                nameupdate, updatename2, 
                numupdate, updatenum
            };
        },
    }
</script>

<style lang="scss" scoped>
.binding_wrap {
    max-width: 1080px;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    gap:60px;
    .container {
        display: block;
        z-index: 999;
        width: calc(50% - 30px);

        h2 {margin-top: 50px;}
        .result { 
            text-align: left;
            margin-bottom: 12px;
            color: rgb(198, 198, 247);
            strong {font-size:18px;}
        }
        .btn_wrap {
            display: flex;
            gap: 12px;
            align-items: center;
            margin-bottom: 30px;
            input {
                width: 80%;
                padding: 10px 20px;
                border-radius: 12px;
                border-bottom: 1px solid #ccc;
            }
            .btn {
                width: calc(20% - 12px);
                &-pri {
                    padding: 10px 0;
                    text-align: center;
                    border-radius: 12px;
                    background: #333;
                    color: #fff;

                }
            }
        }
        
    }
}
</style>