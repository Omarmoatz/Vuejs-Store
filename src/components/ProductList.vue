<template>
  <div class="container-fluid my-5">
    <h4> Products</h4>
    <div class="row">

      <div class="col-lg-3 my-5" v-for="product in products_props" :key="product.id">
        <div class="card">
        <img :src="product.image" class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">{{ product.name }} </h5>
            <RouterLink class="btn btn-primary" :to="'/' + product.id">Detail</RouterLink>
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