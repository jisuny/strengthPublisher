<template>
    <div class="area area_c">
        <div 
        class="text text_c"
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
    methods:{
        changePtext(){
            this.$emit('changePtext','Click Children Btn'); //부모 컴포넌트에 보낼 함수명, 보내고 싶은 데이터
        },  
    },
}

</script>

<style lang="scss" scoped>

</style>