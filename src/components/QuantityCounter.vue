<template>
  <div>
      <button v-on:click='decrement()'>-</button>
      <label>&nbsp;{{counter}}&nbsp;</label>
      <button v-on:click='increment()'>+</button>
  </div>
</template>


<script>
export default {
  props: {
    item: {
    }
  }, 
  data() {
    return {
      counter:0
    }
  },
  
  methods:{
      decrement() {
        if(this.counter>0)
          this.counter--;
        else
          this.counter;
        this.$emit('counter', this.item, this.counter)
      },
      increment() {
        if(this.counter<10)
          this.counter++;
        else
          alert('You cannot buy more than 10 items')
        this.$emit('counter', this.item, this.counter)
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button {
  background-color:rgb(139, 158, 190);
  font-size:25px;
  border-radius: 10px;
  text-align: center;
  display:inline-block;
  padding:10px 30px;
  outline: none;
}

label {
  width:100px;
  font-size: 30px;
}
</style>