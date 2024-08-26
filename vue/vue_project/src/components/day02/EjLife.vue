<template>
    <div>
        <h3>은지의 라이프 사이클 익히기</h3>
        <div class="exam" ref="exam" :class="data"> <!-- 접근대상:ref // 사용대상: this.refs  -->
            {{ data }}
        </div>
    </div>
</template>

<script>
//mounted / created

export default {
    name: 'EjLife',
    props: ["propData"],
    data() {
        console.log ("data", this.propData);
        console.log ("=====");
        return {
            data: this.propData,
        };
    },
    //[5-0]_데이터 변화시
    computed: {
        computedData() {
            console.log("computed", this.data + "!~!!")
            console.log("==========");
            return this.data + "!~!!";
        },
    },
    //[5-1]_데이터 변화시
    watch: {
        computedData: {
            immediate: true,
            handler () {
                console.log("watch");
                console.log("=========================");
            },
        },
    },
    methods: {
        myMethod(){
            console.log("method");
            console.log("-----------------");
        }
    },
    //[1]
    beforeCreate() {
        console.log("beforeCreate");
        console.log("props", this.$props);
        console.log("===========");
    },
    //[2]_data생성.computed생성.watch생성.method생성
    created() {
        this.myMethod();
        console.log("created");
        console.log("--------------------------------------");
    },
    //[3]
    beforeMount() {
        console.log("beforeMount");
        console.log("===");
        setTimeout(
            function(){
                console.log("변환 전-", this.data);
                this.data = "bye";
                console.log("변환 후-", this.data);
                console.log("-----");
            }.bind(this), 1000 //만료된 함수 한번 더 실행
        );
    },
    //[4]
    mounted() {
        console.log("mounted");
        console.log("refs", this.$refs.exam); //refs, <div class="exam">000</div>
        console.log("el", this.$el); // el, <template> 내역전체
        console.log("//");
    }, //mounted 후 exam bye <div> 생성
    //[5-2]_데이터 변화시
    beforeUpdate() {
        console.log("beforeUpdate");
        console.log("data", this.data); //data bye
        console.log("ref", this.$refs.exam.textContent); //ref
        console.log("--");
    },
    //[5-3]_데이터 변화시
    updated() {
        console.log("updated");
        console.log("data", this.data); // data bye
        console.log("ref", this.$refs.exam.textContent); //ref bye
        console.log("=======");
    },
    //[6]
    beforeUnmount() {
        console.log("beforeUnmount");
        console.log("this", this);
        console.log("-=-=-=-=");
    },
    //[7]
    unmounted() {
        console.log("unmounted");
        console.log("---++");
    }
};
</script>

<style lang="scss" scoped>
    
</style>
