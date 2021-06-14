<template>
    <div>
        <h1>Your Product</h1>
       <CartItemCard 
       v-for="product in items"
       :key="product.id"
       :product="product"
       />

    </div>
</template>
<script>
import CartItemCard from '../components/cart/CartItemCard.vue'
export default {
    components:{
        CartItemCard
    }
    ,
    computed:{
        items(){
            return this.$store.getters.cartItems
        }
    }
}
</script>