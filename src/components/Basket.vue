<template>
  <div>
    <p>You currently have: </p>
    <ul>
        <li v-for="name in itemsSelected" v-bind:key="name">
          {{ name }}
        </li>
    </ul>
  </div>
</template>


<script>
export default {
  props: {
    itemsSelected: {
      type: Array
    }
  },
  data() {
    return {

    }
  },

  components: {
  },

  methods:{
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>