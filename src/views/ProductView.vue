<template>

  <div class="container">
    <div class="row">
      <div class="col-lg-3">
        
        <FilterProducts />
      </div>
      <div class="col-lg-9">
        <ProductList />
      </div>
    </div>
  </div>




</template>

<script >
import ProductList from '@/components/ProductList.vue';
import FilterProducts from '@/components/FilterProducts.vue';

export default {
    name: 'ProductView',
    components:{
      ProductList,
      FilterProducts
    }
  }

</script>