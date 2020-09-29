<template>
  <div>
    <h1>Shopping Basket</h1>
    <page-content v-bind:itemsList = "itemsList"></page-content>
  </div>
</template>

<script>
// import QuantityCounter from './components/QuantityCounter.vue'
import PageContent from './components/PageContent.vue'

export default {
  data () {
    return {
        itemsList: [
            {
                id: "#000",
                name: "Eggs",
                imageURL: "https://assets.tetrapak.com/static/publishingimages/find-by-food/rollup/food/eggs.jpg",
                show: false,
                price: 2.50
            },
            {
                id: "#025",
                name: "Toast",
                imageURL: "https://www.shareicon.net/data/256x256/2015/11/01/148235_food_256x256.png",
                show: false,
                price: 2
            },
            {
                id: "#067",
                name: "Asparagus",
                imageURL: "https://ui.assets-asda.com/dm/asdagroceries/5010046011880_T1?defaultImage=asdagroceries/noImage&resMode=sharp2&id=BqCRt0&fmt=jpg&fit=constrain,1&wid=256&hei=256",
                show: false,
                price: 3.50
            },
            {
                id: "#077",
                name: "Apple",
                imageURL: "https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTiJjgL7A-zyIqrMLECJ5yggmcduT2CQg8fGQ&usqp=CAU",
                show: false,
                price: 0.70
            },
            {
                id: "#099",
                name: "Ice Cream",
                imageURL: "https://assets.tetrapak.com/static/publishingimages/find-by-food/rollup/extruded-ice-cream.jpg",
                show: false,
                price: 1.00
            },
            {
                id: "#200",
                name: "Crab",
                imageURL: "https://is1-ssl.mzstatic.com/image/thumb/Purple30/v4/67/07/46/6707465a-5cda-f149-7b48-1962f2556e5f/source/256x256bb.jpg",
                show: false,
                price: 45.00
            }
        ]
    }
  },
  components: {
    // QuantityCounter,
    PageContent
  }
}
</script>

<style>
body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

h1 {
  text-align: center;
  background-color: rgb(255, 255, 162);
  padding: 20px;
  margin-top: 0;
  color: orangered;
}

</style>

