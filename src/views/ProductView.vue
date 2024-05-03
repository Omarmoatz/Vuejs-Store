<template>

  <div class="container">
    <div class="row">
      <div class="col-lg-3">
        
        <FilterProducts @selected_data="filter_data" />
      </div>
      <div class="col-lg-9">
        <ProductList :products_props="filterProducts" />
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
          product: tempData,
          filterProducts: tempData
        }
      },
      methods: {
        filter_data(selectedBrands){
          if (selectedBrands.length == 0) {
            this.filterProducts = this.product
          }
          else{
            this.filterProducts = this.product.filter(product => selectedBrands.includes(product.brand_id))
          }

        }
      }
    }

</script>