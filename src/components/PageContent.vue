<template>
  <div>
    <basket v-bind:itemsSelected = "itemsSelected"></basket>
    <ul>
        <li v-for="item in itemsList" v-bind:key="item.id">
            <h2>{{item.name}}</h2>
            <img v-bind:src="item.imageURL" />
            <br>
            <button id="priceBtn" v-on:click="pressShow(item)"><b>{{item.show ? "Hide Price" : "Show Price"}}</b></button>
            <h4 v-show="item.show">${{item.price}}</h4>
            <QuantityCounter v-bind:item="item" v-on:counter="onCounter"></QuantityCounter>
        </li>
    </ul>
  </div>
</template>


<script>
// Local registration of component
import QuantityCounter from './QuantityCounter.vue'
import Basket from './Basket.vue'

export default {
  props: {
    itemsList: {
      type: Array
    }
  },
  data() {
    return {
      itemsSelected: []
    }
  },

  components: {
      QuantityCounter,
      Basket
  },

  methods:{
    pressShow: function (item) {
      item.show = !item.show;
    },
    // Object keys can only be strings.

    onCounter: function (item, count) {
      if (count > 0 && this.itemsSelected.indexOf(item.name) == -1) {
        this.itemsSelected.push(item.name)
      } else if (count == 0) {
        this.itemsSelected.splice(this.itemsSelected.indexOf(item.name), 1);
      }
    }
  },

  watch: {
    itemsSelected: function (val) {
      console.log(val)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#itemsList {
    width: 100%;
    max-width: 1200px;
    margin: 30px auto;
    padding: 0 5px;
    box-sizing: border-box;
}
ul {
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
}
li {
    flex-grow: 1;
    flex-basis: 300px;
    text-align: center;
    padding: 10px;
    border: 1px solid #222;
    margin: 10px;
}
img {
  width:100px;
  height:100px;
}
button {
  margin-bottom: 10px;
  border-radius: 8px;
  padding: 12px 28px;
  background-color: #4CAF50;
  border: 2px solid #4CAF50;
  color: white;
  cursor: pointer;
  outline: none; /* removes the outer border when button is in focus */
}
button:hover {
  background-color: white;
  color: #4CAF50;
}
</style>