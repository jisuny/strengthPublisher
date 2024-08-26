<template>
    <div>
        <h2>Day 03 - 데이터 바인딩 익히기 <br> <sub>vue3 기준</sub></h2>        
        
        <JiBind />
        <EjBind />
    </div>
</template>

<script>
import JiBind from '../../components/day03/JiBind.vue'
import EjBind from '../../components/day03/EjBind.vue'

export default {
    //** components 지역등록**
    components: {
        JiBind,
        EjBind
    },
    data(){
        return{

        };
    },
};
</script>