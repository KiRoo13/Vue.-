<template >
   <div>
      <div v-for="Item in PaymentList" :key="Item.value">
         {{ Item }}
      </div>
   </div>
</template>
<script>
export default {
   name: "PaymentDisplay",
   props: {
      PaymentList: {
         type: Array,
         default: ()=> []
      }
   },
   data () {
      return {
         
      }
   }
}
</script>
<style >
   
</style>