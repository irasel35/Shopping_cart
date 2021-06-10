<template>
  <div class="home">
    <ProductDescriptionEach 
    :product="product"
    :active="active.product_each"/>


    <div class="product-cards-container"></div>
   <ProductSummaryCard 
   v-for="product in items" 
   :key="product.id"
   :product="product"
   v-on:view-product="viewProduct($event)"
   />



    
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import items from '../data/items.js'
import ProductSummaryCard from '../components/products/ProductSummaryCard.vue'
import ProductDescriptionEach from '../components/products/ProductDescriptionEach.vue'

export default {
  name: 'Home',
  components: {
    ProductSummaryCard,ProductDescriptionEach
    
  },
  data(){
    return{
      items:items,
      product:null,
      active : {
        product_each:true

      }

    }
  },
  methods:{
    viewProduct(product){
      this.product=product
      //console.log(this.product)

    }
  }
}
</script>
<style lang="scss">
.product-cards-container{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;

}

</style>
