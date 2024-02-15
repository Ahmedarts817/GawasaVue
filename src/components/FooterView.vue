<template>
  <nav class="footer py-5">
    <div class="container">
      <div class="row mb-4">
        <div class="col-lg-6 col-xl-4">
          <h3 class="brand text-center">
            <i class="whatsapp"
              ><font-awesome-icon icon="fa-brands fa-whatsapp"
            /></i>
            01092615290
          </h3>
          <div class="stores d-flex justify-content-center mt-3">
            <img src="../assets/Huawei-icon.png" alt="" />
            <img src="../assets/google-play.svg" alt="" />
            <img src="../assets/app-store.svg" alt="" />
          </div>
        </div>
        <div class="col-lg-6 col-xl-4">
          <h3 class="brand text-center my-3">احمد عبدالمقصود لخدمات المحمول</h3>
          <ul class="social d-flex justify-content-center gap-2 fs-3">
            <a href="https://www.facebook.com/profile.php?id=61551772168568">
              <i class="text-primary"
                ><font-awesome-icon icon="fa-brands fa-facebook " /></i
            ></a>

            <i class="text-danger"
              ><font-awesome-icon icon="fa-brands fa-youtube"
            /></i>
            <i class="text-info">
              <font-awesome-icon icon="fa-brands fa-twitter"
            /></i>
          </ul>
        </div>
      </div>
    </div>
  </nav>
</template>
<script>
export default {
  name: "FooterView",
};
</script>
<style scoped>
.footer {
  background-color: #feee00;
  position: absolute;
  width: 100%;
  bottom: 0;
  left: 0;
  margin-top: 700px;
}
img {
  widows: 100px;
  height: 30px;
}
.stores img:hover,
.social i:hover {
  opacity: 0.8;
}
.whatsapp {
  color: #25d366;
}
</style>
