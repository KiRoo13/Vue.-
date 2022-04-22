<template>
  <div id="app">
     <HelloWorld></HelloWorld>
     <main>
       <AddPayment @AddNewPayment="AddPaymentData"></AddPayment>
       <PaymentDisplay :PaymentList="PaymentList"></PaymentDisplay>
     </main>
  </div>
</template>


<script>
import HelloWorld from '@/components/HelloWorld.vue'
import PaymentDisplay from './components/PaymentDisplay.vue'
import AddPayment from './components/AddPayment.vue'




export default {
  name: 'App',
  components: {
    HelloWorld,
    PaymentDisplay,
    AddPayment,
},
  data(){
    return {
       PaymentList: [],
       show: true
    }
  },
      methods: {
      getfetch () {
        return  [
        {
            date: '28.03.2020',
            category: 'Food',
            value: 169,
        },
        {
            date: '24.03.2020',
            category: 'Transport',
            value: 360,
        },
        {
            date: '24.03.2020',
            category: 'Food',
            value: 532,
        },
      ]
    },
    AddPaymentData (data){
         this.PaymentList.push(data)
    }
  },
  created() {
    this.PaymentList = this.getfetch()
  },
}
</script>


<style lang="scss">

</style>
