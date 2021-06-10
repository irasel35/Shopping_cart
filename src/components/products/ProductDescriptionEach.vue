<template>
    <div class="Each-background" :class="{show:active}" @click="$emit('close-product-each')">
        <div class="each" :show="{show:active}">
            <div class="each-close" @click="$emit('close-product-each')">close</div>
            <div v-if="product" class="product-details">
                <h3 class="text-center">{{product.name}}</h3>
                <p class="description">{{product.description}}</p>
                <h3 class="text-center">${{product.price.toFixed(2)}}</h3>
            </div>
            <div class="cart-total" v-if="product_total">
                <h3>In Cart</h3>
                <h4>{{product_total}}</h4>

            </div>
            <div class="button-containar">
                <button class="remove">remove</button>
                <button class="add">add</button>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props:[
        'product',
        'active'
    
    ],
    computed:{
        product_total(){
            return 100.00
        }

    }
}
</script>
<style lang="scss">
.Each-background {
    width: 100%;
    height:100vh ;
    position: fixed;
    left: 0;
    top: 0;
    background-color:rgba(124, 124, 125 ,0.60) ;
    z-index: 100;
    display: none;
    transition: display .5s;
    &.show{
        display: block;
    }
}

</style>