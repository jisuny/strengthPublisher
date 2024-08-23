<template>
    <div class="Text_btn">
        <span class="ic">+</span>
        <div class="btn_txt_wrap">
        <!-- <div class="btn_txt_wrap" v-html="btn_txt_wrap" /> -->
            <h3>{{btn_tit}}</h3>
            <p>{{btn_p}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'BtnEj',
        props: ['btn_tit', 'btn_p']
        // props: ['btn_txt_wrap']
    };
</script>

<style lang="scss" scoped>
    .Text_btn {
        width:290px;
        height:90px;
        background:#342f31;
        border-radius:46px;
        padding:28px 27px;
        margin:20px auto 0;
        cursor: pointer;

        display:flex;
        align-items:center;
        gap:12px;
        
        .ic {
            width:36px;
            height: 36px;
            line-height:35px;
            font-size:30px;
            font-weight: bold;
            border-radius:50%;
            background:#d7aefb;
            color:#342f31;
        }
        .btn_txt_wrap {
            h3{
                font-size:24px;
                font-weight:bold;
                color:#f9eef1;
                // margin-bottom:8px;
            }
            p{
                font-size:19px;
                color:#cec4c7;
            }
        }
    }
</style>
