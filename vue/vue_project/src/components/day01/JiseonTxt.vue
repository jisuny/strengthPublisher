<template>
    <button>
        <em></em>
        <strong>{{ msg }}</strong>
        <span>{{ subMsg }}</span>
    </button>
</template>

<script>
export default {
    name: 'JiseonTxt',
    props:[
        'msg',
        'subMsg'
    ],
}
</script>

<style lang="scss" scoped>
    button{
        position:relative;
        padding:19px 10px 19px 75px;
        width:290px;
        background-color:#342f31;
        border-radius: 50px;
        em{
            position: absolute;
            left:27px;
            top:50%;
            width:36px; 
            height:36px;
            background-color:#D7AEFB;
            border-radius: 50%;
            transform: translateY(-50%);
            &::before{
                position: absolute;
                top:50%;
                left:50%;
                display: block;
                width:4px;
                height:18px;
                content: '';
                background-color:#342f31;
                transform: translate(-50%, -50%);
            }
            &::after{
                position: absolute;
                top:50%;
                left:50%;
                display: block;
                width:4px;
                height:18px;
                content: '';
                background-color:#342f31;
                transform: translate(-50%, -50%) rotate(-90deg);
            }
        }   
        
        >*{
            text-align: left;
        }
        strong{
            display: block;
            margin-bottom:10px;
            font-size:24px;
            color:#f9eef1;
            font-weight:bold;
            line-height: 1.2;
        }
        span{
            display: block;
            font-size:19px;
            color:#cec4c7;
            font-weight: 600;
            line-height: 1.2;
        }
    }
</style>
