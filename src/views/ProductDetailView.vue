<template>

    <div class="container my-5">
      <div class="row">

        <div class="col-lg-6">
          <img :src="product.image" alt="" width="100%"/>
        </div>

        <div class="col-lg-6 mt-5 border border-1 rounded-3 px-5 py-5">
          <h1>{{ product.name }}</h1>
          <div class="d-flex my-3">
            <h6 class="me-5"><span class="text-primary">brand :</span> {{ product.brand }}</h6>
            <h6 class=""><span class="text-primary">category :</span> {{ product.category }}</h6>
          </div>    
          <p>{{ product.description }}</p>
          <h4 class="text-success" >$ {{ product.price }}</h4>
          <!-- add to cart button -->
          <form class="mt-5" >
            <div class="d-flex">
              <input type="text" class="form-control w-25 me-2">
              <button class="btn btn-success w-100 " >Add to cart</button>
            </div>
          </form>
        </div>

      </div>
    </div>
    

</template>

<script>
  import { tempData } from '@/temp-data';

  export default {
    name: 'ProductDetailView',
    data(){
      return {
        product: tempData.find(product => product.id == this.$route.params.productId)
      }
    }
  }

</script>
