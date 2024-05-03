<template>

    <h1>This is {{ product.name }} Detail page</h1>

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
