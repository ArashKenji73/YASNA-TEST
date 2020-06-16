<template>
    <div class="counter">
        <div class="header">
           Step : {{step}}
        </div>
        
        <h1>{{initLimit}}</h1>

        <button @click.stop="addStepToInit">RUN</button>
    </div>
</template>

<script>
export default {
    data(){
        return{
            init: 0,
        }
    },
    computed:{
        initLimit(){
            return this.init.toFixed(2)
        }
    },
    props:['step'],
    methods:{
        addStepToInit(){
            this.init += parseFloat(this.step);
        }
    }
}
</script>

<style lang="scss" scoped>
.counter{
    width: 150px;
    margin: 0.75rem;
    padding: 1rem;
    //border: 2px solid gray;
    border-radius: 16px;
    box-shadow: 0px 0px 30px #d8d8d8;
    .header{
        padding: 1rem;
        border: 1px solid gray;
        border-radius: 16px;
    }
    button{
        width: 100%;
        padding: 0.5rem;
        background: rgb(19, 149, 255);
        color: #fff;
        border: transparent;
        font-size: 16px;
        border-radius: 16px;
    }
}
</style>