<template>
  <div class="home">
    <div class="top-products py-5 container">
      <h2 class="text-center my-4">أفضل المنتجات</h2>
      <div class="row">
        <div
          v-for="product of products"
          :key="product.id"
          class="col-md-6 col-lg-4 col-xl-3 p-2 mb-5"
        >
          <ProductBox :product="product" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import ProductBox from "@/components/product/ProductBox.vue";
import categoriesMixin from "@/mixins/categoriesMixin";
import productsMixin from "@/mixins/productsMixin";
export default {
  name: "HomeView",
  components: { ProductBox },
  mixins: [categoriesMixin, productsMixin],
};
</script>
<style scoped>
.categories-nav a {
  display: block;
  color: #000000;
  padding: 10px;
}
.categories-nav a:hover {
  background-color: #fff;
  box-shadow: 15px 25px 36px -4px rgba(0, 0, 0, 0.1);
}
</style>
