<template lang="">
   <div>
      <div>
         <button @click="Show">Add new cost</button>
      </div>
     <div v-show="show">
         <input v-model="data" placeholder="data" type="text">
         <input v-model="category" placeholder="dcategory" type="text">
         <input v-model="value" placeholder="value" type="text">
         <button @click="OnClick">Save</button>
     </div>
   </div>
</template>
<script>
export default {
   name: "AddPayment",
   data (){
      return {
         data: "",
         category: "",
         value: "",
         show: false
      }
   },
   computed: {
         getCurrentDay (){
            const day = new Date()
            const d = day.getDate()
            const m = day.getMonth()+1
            const y = day.getFullYear()
            return `${d} ${m} ${y}`
         }
   },
   methods: {
      OnClick () {
           const data = {
              data: this.data || this.getCurrentDay,
              category: this.category,
              value: this.value
           }
           this.$emit("AddNewPayment", data)
      },
         Show (){
            this.show = true 
         }
   },
}
</script>
<style lang="">
   
</style>