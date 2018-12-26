<template>
  <li v-on:click="delList"></li>
</template>

<script>
export default {
 props:['index'],
 methods: {
   delList:function(){
     this.$emit("moveList",this.index)
   }
 },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
