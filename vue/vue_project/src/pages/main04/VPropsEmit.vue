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

        <div class="ejArea">
            <h3 class="h3_ej">== EJ_Props/Emit ==</h3>
            <!-- <div class="event_state">
                <EventView 
                :event="eventName" 
                @sendMsg="receiveMsg"
                />                 -->
                <!-- @자식 컴포넌트에서 보낸 함수명="부모에서 받는 메서드 명" -->
                <!-- {{ Msg }}
            </div> -->

            <div class="area area_p">
                <div class="text text_p">
                {{TextP}}
                </div>
                <button 
                class="btn btn_p"
                @click="changeCtext"
                >
                <!-- //자.vue에서 정의한 props 이름인 changeTextC에 data 변수명 changeC정의 -->
                changeC
                </button>
            </div>
            <AreaChild
            @changePtext="receiveBtnC"
            :TextC="changeCtext" 
            />
            <!-- :TextC="TextC" //하위컴포넌트바인드 -->
            <!-- @changePtext : 자식 vue에서 받아옴 -->
            <!-- 받는 부분X 받아오는 컴포넌트에 v-on 값 붙여야 작동 -->
            <!-- :TextC -> 자식 vue에 전달 값 -->
        </div>
    </div>
</template>

<script>
// import EventView from '../../components/day04/EjChildren.vue';
import AreaChild from '../../components/day04/EjChildren02.vue';

export default {
    //** components 지역등록**
    components: {
        // EventView,
        AreaChild,
    },
    data(){
        return{
            // eventName:'20주년 맞이 고객 감사 이벤트',
            // Msg:'',

            TextP:'ParentTextArea',
        };
    },
    methods: {
        // receiveMsg(Msg){
        //     this.Msg=Msg; 
        //     //자식에서 보낸 데이터를 receiveMsg에 담아, 부모파일의 {{Msg}}에 매핑해 화면 반영
        // },
        receiveBtnC(TextP){
            this.TextP=TextP;
        },
        changeCtext(){
            this.props('TextC','Click Parent Btn')
        }
    },
};
</script>

<style lang="scss">
    .h3_ej {margin-top:100px;}
    .event_state {
        margin: 120px auto 200px;
        color: rosybrown;
    }

    .area {
        width: 355px;
        display: flex;
        gap:15px;
        align-items: center;
        margin: 20px auto 100px;
        &_p {margin:20px auto 30px;}

        .text {
            width: 240px;
            height: 40px;
            background: #f3f3f3;
            border: 1px solid #f1e0ff;
            border-radius: 10px;
            color: #444;
            line-height: 38px;
            padding: 0 10px;
        }

        .btn {
            width: 100px;height: 40px;
            line-height: 38px;text-align: center;
            border: 1px soild #c5c5c5;
            border-radius: 10px;
            &_p {background: #f9eef1;}
            &_c {background: #f1e0ff;}
        }
    }
    
</style>
