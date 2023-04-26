<template>
  <div class="calculate">
    <input type="text" v-model="result" placeholder="0">
    <div class="nubers-group">
      <button class="number" @click="input(num)" v-for="num in numbers" :key="num">{{ num }}</button>
      <button class="option" @click="input(op)" v-for="op in options" :key="op">{{ op }}</button>
      <button class="reset" @click="reset()">c</button>
      <button class="calc" @click="calc()">=</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      result: "",
      numbers: [1,2,3,4,5,6,7,8,9,0],
      options: ['+','-','*','/'],
    }
  },
  methods: {
    input: function(char) {
      this.result = this.result.toString();
      this.result +=char;
    },
    reset: function() {
      this.result = '';
    },
    calc: function() {
      this.result = eval(this.result);
    }
  }
}
</script>

<style scoped>
  .calculate {
    display: flex;
    flex-direction: column;
    width: 200px;
    flex-wrap: wrap;
  }

  .number {
    width: 33%;
    height: 40px;
    background-color: rgba(76, 72, 72, 0.212);
    border: 1px solid rgb(122, 124, 122);
    cursor: pointer;    
  }

  .option {
    width: 33%;
    height: 40px;
    background-color: orange;
    border: 1px solid rgb(124, 84, 8);
    cursor: pointer;  
  }

  .number:hover {
    background-color:  rgba(126, 120, 120, 0.212);
  }

  .nubers-group {
    display: flex;
    flex-wrap: wrap;
    width: 200px;
  }
  .reset {
    width: 33px;
    background-color: orange;
    border: 1px solid rgb(124, 84, 8); 
    cursor: pointer;     
  }

  .calc {
    width: 33px;
    background-color: orange;
    border: 1px solid rgb(124, 84, 8);
    cursor: pointer;  
  }

  .reset:hover {
    background-color: rgb(245, 172, 38);
  }

  .calc:hover {
    background-color: rgb(245, 172, 38);
}

</style>
