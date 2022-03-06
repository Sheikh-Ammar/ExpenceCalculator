<template>
<div v-if="status">
<div class="model" @click.self="toggle">
    <div class="model-container">
        <div class="model-form">
            <form @submit.prevent="addExpence">
                <div class="model-group">
                    <h3>Add Expense</h3>
                </div>
                <div class="model-group">
                    <input type="text" name="" id="" class="model-control" placeholder="Enter Title...." v-model="title">
                </div>
                 <div class="model-group">
                    <input type="number" name="" id="" class="model-control" placeholder="Enter Expense...." v-model="number">
                </div>
                 <div class="model-group">
                    <input type="submit" value="Add Expense" class="btn">
                </div>
            </form>
        </div>
    </div>
</div>
</div>
</template>

<script>
export default {
    name: "ModelForm",
    props: ["status"],
    data(){
        return{
            title: "",
            number: "",
        };
    },
    methods: {
        toggle(){
            this.$emit("modelHide");
        },
        addExpence(){
            this.$emit("storeExpence", {title:this.title, number:this.number});
            this.title = "";
            this.number = "";
        }
    },
}
</script>

<style scoped>
.model{
    z-index: 1000;
    display: flex;
    justify-content: center;
    align-items: center;
    position: fixed;
    top: 0; left: 0; right: 0;
    width: 100%; height: 100%;
    background-color: rgba(0,0,0,0.8);
}
.model-container{
    background-color: #fff;
    width: 450px;
    padding: 20px;
    border-radius: 5px;
}
.model-group{
    margin: 15px 0px;
}
.model-control{
    outline: none;
    border-left: none; border-right: none; border-top: none;
    border-bottom: 10px solid sliver;
    width: 100%;
    padding: 7px 0px;
}
.btn{
    border: none;
    border-radius: 3px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
    background-color: #034f1e;
    color: #fff;
    cursor: pointer;
    width: 100%;
    padding: 10px 15px;
}
</style>