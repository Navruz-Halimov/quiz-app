<template>
  <div id="app">
    <h1>Math Quiz App</h1>
    <OperatorQuiz @onBack="clearOperator" v-if="operator" :operator="operator" />
  <OperatorSelector v-if="!operator" @changeOperator="changeOperator" />
  </div>
</template>
<script>

import OperatorSelector from './components/OperatorSelector';
import OperatorQuiz from './components/OperatorQuiz';
export default {
  components:{
    OperatorQuiz,
    OperatorSelector
  },
  data(){
return{
operator:null,
    }
  },
  methods:{
    changeOperator(operator){
      console.log(operator)
      this.operator=operator;
    },
    clearOperator(){
      this.operator=null;
    }
  }
}
</script>
<style lang="scss">
button{
  padding: 10px;
  background-color: #10aeb2;
  color:white;
  width: 160px;
  height: 80px;
  font-size: 24px;
  cursor: pointer;
  border: none;
  margin-left: 5px;
  margin-right: 5px;
  vertical-align: top;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
