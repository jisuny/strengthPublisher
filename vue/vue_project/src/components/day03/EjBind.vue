<template>
<div class="binding_wrap">
    <div class="container">
        <h2>V-bind</h2>
        <div class="name">{{name}}</div>
        <div class="btn_wrap">

            <input type="text" v-bind:value="name">
            
            <button class="btn btn-pri" v-on:click="updateResult">
                Click
            </button>
        </div>
    </div>
    <div class="container">
        <h2>V-bind:type | V-model</h2>
        <div class="name">{{valueNum}}</div>
        <div class="btn_wrap">

            <input :type="type" v-model="valueNum" placeholder="숫자입력">
            
            <!-- <button class="btn btn-pri" v-on:click="updateResult">
                Click
            </button> -->
        </div>
    </div>
</div>
</template>

<script>

    import {ref} from 'vue'

    export default {
        name:'EjBind',

        data(){
            return {
                valueNum : "0",
            }
        },

//composition API
        setup() { //vue.js3 부터 setup 기능_ 
            let name= ref("input01");
            let type= ref("number")

            var updateResult = ()=>{
                name.value="result";
                // type.value="33"
                console.log(name);
            }

            return{
                name, updateResult, type
            };
        }
    }
</script>

<style lang="scss" scoped>
.binding_wrap {
    max-width: 1080px;
    margin: 0 auto;
    display: flex;
    gap:60px;
    .container {
        display: block;
        z-index: 999;
        width: 50%;

        h2 {margin-top: 50px;}
        .name { 
            text-align: left;
            margin-bottom: 12px;
            color: rgb(198, 198, 247);
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