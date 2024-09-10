<template>
    <div class="area area_c">
        <div 
        class="text text_c"
        @changeCtext="reciveBtnP"
        >
            {{TextC}}
        </div>
        <button 
        class="btn btn_c"
        @click="changePtext"
        >
        changeP
        </button>
    </div>
</template>

<script>
export default {
    // name: 'AreaChild',

    methods:{
        changePtext(){
            this.$emit('changePtext','Click Children Btn'); //부모 컴포넌트에 보낼 함수명, 보내고 싶은 데이터
        },  
        reciveBtnP(TextC){
            this.TextC=TextC;
        }
    },
    // 자식text
    props:['changeCtext'],
    // props: {
    //     TextC: {
    //         type:String,
    //         default:'ChildTextArea'
    //     },
    //     setup(){
    //         return{
    //             reciveBtnP:'Click Parent Btn'
    //         }
    //     }
    // }, 
    data(){
        return{
            TextC : 'ChildTextArea'
        }
    }
}

</script>

<style lang="scss" scoped>

</style>