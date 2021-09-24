<template>
<div>
    <button @click="change" >点我显示/隐藏</button>
    <div v-show="isShow"
         class="box come"
         
        ></div>
</div>
</template>

<script>
export default {
    name:"Test",
    data(){
        return{
            isShow:true
        }
    },
    methods:{
        change(){
            this.isShow = !this.isShow
        }
    }
}

</script>

<style>
.box{
    height: 100px;
    width: 500px;
    background-color: blue;
    margin-top: 20px;
}
@keyframes move{
    from{
        transform: translateX(-100%);
    }
    to{
        transform: translateX(0);
    }
    }
    .come{
    animation: move 1s;
    }
    .go{
    animation: move 1s reverse;
    }
</style>