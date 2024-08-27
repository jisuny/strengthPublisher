<template>
    <div>
        <h2>Day 04 - props (부모 -> 자식) && emit (자식 -> 부모) 익히기 <br> <sub>vue3 기준</sub></h2>
        <p>부모 버튼을 누르면 자식 div에 데이터 출력, 자식버튼을 누르면 부모 div에서 데이터 출력</p>
        <a 
            href="https://www.figma.com/design/M2IFiNPEBHRonQKvPLLRTy/vue_project?node-id=2-2&m=dev&t=yEkzbaPuB3iYiJgg-1" 
            target="_blank" 
            title="새창열림"
            :class="'link_txt figma'"
        >
            <span>피그마 바로가기</span>
        </a>
        <div class="img_area">
            <img src="../../assets/images/day04/day04_props_emit.png" alt="props와 emit">
        </div>


    </div>
</template>

<script>

export default {
    //** components 지역등록**
    components: {
    },
    data(){
        return{

        };
    },
};
</script>