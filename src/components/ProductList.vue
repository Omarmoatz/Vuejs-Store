<template>
  <div class="container-fluid my-5">
    <h4> Products</h4>
    <div class="row">

      <div class="col-lg-3 my-5" v-for="product in products_props" :key="product.id">
        <div class="card">
        <img :src="product.image" class="card-img-top px-3 py-3 rounded-1" alt="...">
          <div class="card-body text-center">
            <h5 class="card-title fs-3 ">{{ product.name }} </h5>
            <div class="d-flex my-3">
              <h6 class="text-danger text-decoration-line-through mx-3 fs-5" >$ 1000 </h6>
              <h6 class="text-success fs-4" >$ {{ product.price }}</h6>
            </div>
            
            <RouterLink class="btn btn-outline-primary px-5" :to="'/' + product.id">Detail</RouterLink>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>


<script >

  export default {
    name: 'ProductList',
    props: ['products_props'],
  }

</script>

<style scoped> 
/* scoped  is used here so that the css only applies
 to this component and not other components with the same tag */

img{
  width: 216px;
  height: 205px;
}

</style>