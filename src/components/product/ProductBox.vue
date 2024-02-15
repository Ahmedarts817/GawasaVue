<template>
  <router-link :to="{ name: 'productDetails', params: { id: product._id } }">
    <div class="text-center">
      <img :src="product.imageCover" alt="" class="card-img-top" />
    </div>
    <div class="card-body text-center mt-3 cursor-pointer">
      <p>ج.م {{ product.price }}</p>
      <h5>{{ product.title }}</h5>
      <div class="stars">
        <i class="text-dark"><font-awesome-icon icon="fa-solid fa-star" /></i>
        <i class="text-warning"
          ><font-awesome-icon icon="fa-solid fa-star"
        /></i>
        <i class="text-warning"
          ><font-awesome-icon icon="fa-solid fa-star"
        /></i>
        <i class="text-warning"
          ><font-awesome-icon icon="fa-solid fa-star"
        /></i>
        <i class="text-warning"
          ><font-awesome-icon icon="fa-solid fa-star"
        /></i>
      </div>
      <router-link
        :to="{ name: 'editProduct', params: { id: this.product._id } }"
        v-show="$route.name === 'adminproducts'"
        ><a class="m-4 btn btn-primary" href="">Edit</a></router-link
      >
      <button
        @click="deleteProduct"
        class="m-4 btn btn-primary"
        href=""
        v-show="$route.name === 'adminproducts'"
      >
        Delete
      </button>
    </div>
  </router-link>
</template>

<script>
import axios from "axios";

export default {
  name: "ProductBox",
  props: ["product"],
  data() {
    return {
      baseUrl: "http://localhost:8000/api/v1/",
    };
  },

  methods: {
    async deleteProduct() {
      await axios({
        method: "delete",
        url: `${this.baseUrl}products/${this.product._id}`,
        headers: { Authorization: `Bearer ${localStorage.getItem("token")}` },
      })
        .then(
          setTimeout(() => {
            window.location.reload();
            console.log("done");
          }, 1)
        )
        .catch((err) => console.log(err));
    },
  },
};
</script>
