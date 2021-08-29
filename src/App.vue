<template>
  <div id="app">
    <button @click="addArr">Add {{ arrLength }}</button>
    <div class="container">
      <div v-for="(item, index) in arr" :key="index"></div>
    </div>
    <div class="limit">
      <div
        v-for="(item, index) in limit"
        :key="index"
        :style="{ backgroundColor: item }"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      limit:[],
      arr:[1],
    }
  },
  computed:{
    arrLength(){
      return this.arr.length
    }
  },
  methods: {
    addArr(){
      if(this.limit.length === 4)
      return
      this.arr.push(1);
    }
  },

  watch: {
    arrLength: function(newArr){

      switch(newArr){
        case 5:
          this.limit.push('green')
          break;
        case 10:
          this.limit.push('yellow')
          break;
        case 20:
          this.limit.push('orange')
          break
        case 30:
          this.limit.push('red')
          break
      }
    
    }
  },
};
</script>

<style scoped>
body {
  margin: 50px;
  font-family: monospace;
}

.container {
  background-color: #dddddd;
  padding: 10px;
  height: 400px;
  display: flex;
  flex-wrap: wrap;
}

.container div {
  height: 100px;
  width: 100px;
  margin: 10px;
  background-color: rgb(82, 122, 82);
}

.limit {
  display: flex;
  margin-top: 20px;
}

.limit div {
  margin-right: 20px;
  height: 20px;
  width: 200px;
  background-color: #c3bfbf46;
}
</style>
