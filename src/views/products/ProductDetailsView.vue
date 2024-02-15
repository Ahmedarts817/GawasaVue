<template>
  <div class="container">
    <h1 class="p-3 mb-5 text-center">طلب المنتج</h1>
    <div class="row">
      <div class="col text-center">
        <h3 class="mb-3">{{ product.title }}</h3>
        <div class="text-center">
          <img :src="product.imageCover" width="400" alt="" />
        </div>
        <p class="mt-3">السعر {{ product.price }} ج.م</p>
        <a
          class="btn btn-success d-block mx-auto mt-3 fs-5 w-25"
          :href="`https://wa.me/00201092615290?text=انا مهتم بشراء منتج ${product.title} ${product.price}جنيه`"
        >
          طلب الان</a
        >
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "ProductDetailsView",
  data() {
    return {
      product: "",
      baseUrl: "http://localhost:8000/api/v1/",
      images: "",
      wishlistItems: [],
      cartItems: [],
      addedToWishlist: false,
      addedToCart: false,
    };
  },
  computed: {
    itemIsInWishlist() {
      return this.wishlistItems.some((item) => this.product._id == item._id);
    },
    itemIsInCart() {
      return this.cartItems.some((item) => this.product._id == item.product.id);
    },
  },
  methods: {
    async fetchData() {
      await axios
        .get(`${this.baseUrl}products/${this.$route.params.id}`)
        .then((res) => {
          this.product = res.data.data;
        })
        .catch((err) => console.log(err));
    },
  },
  mounted() {
    this.fetchData();
  },
};
</script>
