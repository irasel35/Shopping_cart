<template>
    <div>
        <h1>Your Product</h1>
       <CartItemCard 
       v-for="product in products"
       :key="product.id"
       :product="product"
       />
       
       <CardSummaryPaymentCard 
      />

    </div>
</template>
<script>
import CartItemCard from '../components/cart/CartItemCard.vue'
import CardSummaryPaymentCard from'../components/cart/CardSummaryPaymentCard.vue'
export default {
    components:{
        CartItemCard,CardSummaryPaymentCard
    }
    ,
    computed:{
        products(){
            return this.$store.getters.cartItems
        }
    }
}
</script>