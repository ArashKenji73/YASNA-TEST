<template>
    <form>
        <input type="number" v-model="step" placeholder="step">
        <button @click.prevent.stop="AddCounter" type="submit">Add Counter</button>
    </form>
</template>
<script>
export default {
    data(){
        return{
            step: ''
        }
    },
    methods:{
        AddCounter(){
            this.$emit("AddCounter", this.step);
            this.step = '';
        }
    }
}
</script>
<style lang="scss" scoped>
form{
    display: flex;
    justify-content: space-between;
    padding: 1rem;

    input[type='number']{
        flex-grow: 1;
        padding: 1rem;
        margin-right: 1rem;
        border-radius: 16px;
    }
    button{
        width: 200px;
        background: rgb(19, 149, 255);
        color: #fff;
        border: transparent;
        font-size: 16px;
        border-radius: 16px;
    }
}
</style>