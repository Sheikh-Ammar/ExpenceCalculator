<template>
<nav>
    <button class="btn" @click="openModel">Add Expense</button>
</nav>
</template>

<script>
export default {
    name: "NavBar",
    methods: {
        openModel(){
            this.$emit("modelShow");
        }
    },
}
</script>

<style scoped>
nav{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 60px;
    background-color: #fff;
    box-shadow: 0px 15px 30px rgba(0,0,0,0.3);
}
.btn{
    border: none;
    border-radius: 3px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
    background-color: #034f1e;
    color: #fff;
    cursor: pointer;
    padding: 10px 15px;
}
</style>