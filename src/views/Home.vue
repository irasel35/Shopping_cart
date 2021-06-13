<template>
  <div class="home">
    <ProductDescriptionEach 
    :product="product"
    :active="active.product_each"
    v-on:close-product-each="closeProducteach()"/>


    <div class="product-cards-container">
   <ProductSummaryCard 
   v-for="product in items" 
   :key="product.id"
   :product="product"
   v-on:view-product="viewProduct($event)"
   />
</div>


    
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
        product_each:false

      }

    }
  },
  methods:{
    viewProduct(product){
      this.product=product
      this.active.product_each=true
      //console.log(this.product)

    },
    closeProducteach(){
      this.active.product_each=false

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
