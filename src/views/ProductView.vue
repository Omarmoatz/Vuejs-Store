<template>
  <div id="carouselExampleCaptions" class="carousel slide">
    <div class="carousel-indicators">
      <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
      <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1" aria-label="Slide 2"></button>
      <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2" aria-label="Slide 3"></button>
    </div>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img :src="img6" class="d-block w-100" alt="...">
        <div class="carousel-caption d-none d-md-block">
          <h5>Welcome To Our Store</h5>
          <p>Some representative placeholder content for the first slide.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img :src="img7" class="d-block w-100" alt="...">
        <div class="carousel-caption d-none d-md-block text-black">
          <h5>I am Omar Moataz the Creator</h5>
          <p>Some representative placeholder content for the second slide.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img :src="img6" class="d-block w-100" alt="...">
        <div class="carousel-caption d-none d-md-block">
          <h5>This is my Vue.js Project</h5>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque laudantium modi laboriosam quo.</p>
        </div>
      </div>
    </div>
    <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
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

  import img7 from '../assets/7.jpg'
  import img6 from '../assets/6.png'

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
          img6 : img6,
          img7 : img7
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