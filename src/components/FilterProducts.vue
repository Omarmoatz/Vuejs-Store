<template>
  <div class="container my-5">
    <h4>Filter</h4>
    <div class="row my-5">
      
      <div class="col-lg-12">

        <div class="card bg-light  py-4">
          <h6 class="border-bottom mx-4 ">Filter by brand</h6>
          <div class="card-body ms-3">

            <div class="form-check" v-for="brand in brands" :key="brand.id">
              <input class="form-check-input" type="checkbox"
              :value="brand.id"  
              v-model="selectedBrands">
              <label class="form-check-label" >
                {{ brand.name }}
              </label>
            </div>

          </div>
        </div>

      </div>
    </div>
  </div>

</template>

<script>

  import { tempData_brands } from '@/temp-data';

  export default {
    name: 'Filter',
    data(){
      return {
        brands: tempData_brands,
        selectedBrands: []
      }
    },
    watch: {
      selectedBrands(){
        this.$emit('selected_data',this.selectedBrands)
      }
    } 
  }
</script>

<style>

body{
  background-color: rgb(230, 228, 228) !important;
}
</style>