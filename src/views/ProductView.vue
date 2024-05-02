<template>

  <div class="container">
    <div class="row">
      <div class="col-lg-3">
        
        <FilterProducts />
      </div>
      <div class="col-lg-9">
        <ProductList :products_props="product" />
      </div>
    </div>
  </div>




</template>

<script >
  import ProductList from '@/components/ProductList.vue';
  import FilterProducts from '@/components/FilterProducts.vue';

  import { tempData } from '@/temp-data';

  export default {
      name: 'ProductView',
      components:{
        ProductList,
        FilterProducts
      },
      data(){
        return {
          product: tempData
        }
      }
    }

</script>