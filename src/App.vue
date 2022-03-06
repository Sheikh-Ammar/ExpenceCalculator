<template>
  <NavBar @modelShow="modleToggle"/>
  <Model @modelHide="modelToggle" :status="modelStatus" @storeExpence="storeExpenceData"/>
  <Expences :allExpences="expences"/>
  <Footer />
</template>

<script>
import NavBar from "../src/components/NavBar.vue"
import Model from "../src/components/Model.vue"
import Expences from "../src/components/Expences.vue"
import Footer from "../src/components/Footer.vue"


export default {
  name: 'App',
  components: {
    NavBar,
    Model,
    Expences,
    Footer,
  },
  data(){
    return{
      modelStatus: false,
      expences: {
        balance: 0,
        income: 0,
        expence: 0,
        history: [],
      }
    };
  },
  methods:{
    modleToggle(){
      this.modelStatus = !this.modelStatus;
    },
    storeExpenceData(result){
      const number = parseInt(result.number); //CONVERT STRING INTO NUMBER
      if (number > 1) {
        this.expences = {
          ...this.expences,
          income: this.expences.income + number,
          balance: this.expences.balance + number,
          history: [{title:result.title, number}, ...this.expences.history],
        }
      } else if(number < 1) {
         this.expences = {
          ...this.expences,
          expence: this.expences.expence + number,
          balance: this.expences.balance + number,
          history: [{title:result.title, number}, ...this.expences.history],
        }
      }
      this.modelStatus = false;
    }
  }
};
</script>

<style>
*{
margin: 0; padding: 0; box-sizing: border-box;
}
body{
  background-color: #fafafa;
}
</style>
