<template>
  <nav class="navbar navbar-expand-lg">
    <div class="container">
      <router-link to="/">
        <a class="brand fw-bold position-relative"
          ><img src="../assets/logo5.png" width="100" alt=""
        /></a>
      </router-link>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0 fw-bold">
          <li class="nav-item" v-bind:hidden="userName">
            <router-link to="/signin"
              ><a class="nav-link login" href=""
                ><font-awesome-icon icon="fa-solid fa-user" /> تسجيل الدخول
              </a></router-link
            >
          </li>
          <li class="nav-item" v-show="userName">
            <a @click="logOut" class="nav-link" href=" "> تسجيل الخروج </a>
          </li>
          <li class="nav-item">
            <a class="nav-link wishlist" href=""
              ><font-awesome-icon icon="fa-solid fa-heart" /> الرغبات
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link cart" href=""
              ><font-awesome-icon icon="fa-solid fa-cart-shopping" /> عربة
              التسوق</a
            >
          </li>
          <li class="nav-item" v-show="userRole === 'admin'">
            <router-link to="/admin"
              ><a class="nav-link" href="">Admin</a>
            </router-link>
          </li>
          <li class="nav-item" v-show="userName">
            <p class="nav-link" href="">Hi {{ userName }}</p>
          </li>
        </ul>

        <a aria-label="Chat on WhatsApp" href="https://wa.me/00201092615290">
          <img
            alt="Chat on WhatsApp"
            src="../assets/WhatsAppButtonGreenSmall.png"
          />
        </a>
      </div>
    </div>
  </nav>
</template>
<script>
export default {
  name: "NavBar",
  props: ["userName", "userRole"],
  methods: {
    logOut() {
      localStorage.removeItem("token");
      this.$router.push("/");
    },
  },
};
</script>
<style scoped>
nav {
  background-color: #feee00;
}
.text-green {
  color: green;
}
</style>
