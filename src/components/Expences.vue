<template>
<div>
    <div class="expences">
    <div class="box balance">
        <span>BALANCE</span>
        <p>Rs&nbsp;{{allExpences.balance}}</p>
    </div>
    <div class="box income">
        <span>INCOME</span>
        <p>Rs&nbsp;{{allExpences.income}}</p>
    </div>
    <div class="box expence">
        <span>EXPENCE</span>
        <p>Rs&nbsp;{{allExpences.expence}}</p>
    </div>
</div>

    <div class="history" v-for="history in allExpences.history" :key="history.title" :class="[history.number > 0  ? 'g-border' : 'r-border']">
        <div class="history-title">{{history.title}}</div>
        <div class="history number">{{history.number}}</div>
    </div>
</div>
</template>

<script>
export default {
    name: "ExpencesCheck",
    props: ["allExpences"],
}
</script>

<style scoped>
.expences{
    width: 80%;
    margin: 70px auto;
    display: flex;
}
.box{
    background-color: #fff;
    padding: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 200px; height: 150px;
    margin: 0px 50px;
    box-shadow: 0 10px 20px rgba(0,0,0,0.5);
    position: relative;
    
}
.box span{
    position: absolute;
    top:0; left: 0;
    color: #fff;
    font-size: 14px;
    padding: 5px 8px;
}
.balance{
    border-bottom: 4px solid orange;
     border-right: 4px solid orange;
}
.balance span{
     background-color:orange;
}
.income{
    border-bottom: 4px solid green;
    border-right: 4px solid green;
}
.income span{
     background-color: green;
}
.expence{
    border-bottom: 4px solid blue;
     border-right: 4px solid blue;
}
.expence span{
     background-color: blue;
}
p{
    font-size: 20px;
    font-weight: bold;
}
.history{
    width: 800px;
    margin: 10px auto;
    background-color: #fff;
    padding: 5px;
    box-shadow: rgb(0,0,0);
    display: flex;
    justify-content: space-around;
    align-items: center;
}
.history-title{
    width: 60%;
    font-weight: bold;
    text-transform: uppercase;
}
.history-number{
    width: 40%;
    text-align: right;
    font-weight: bold;
}
.g-border{
    border: 2px solid green;
}
.r-border{
    border: 2px solid red;
}
@media(max-width:720px) {
    .expences{
        flex-direction: column;
    }
    .box{
        margin: 8px auto;
    } 
}
</style>