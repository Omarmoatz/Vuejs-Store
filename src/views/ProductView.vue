<template>
  <div class=" text-center pb-5 ">
    <img :src="img" class="img-fluid" >
    <h2 class="my-4">Welcome To Our Store</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque laudantium modi laboriosam quo.</p>
  </div>

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

  import img6 from '../assets/7.jpg'

  export default {
      name: 'ProductView',
      components:{
        ProductList,
        FilterProducts
      },
      data(){
        return {
          product: tempData,
          filterProducts: tempData,
          img : img6
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