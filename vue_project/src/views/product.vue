<template>
    <main class="flex-shrink-0" id="home">
            <!-- Navigation-->
            <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
                <div class="container px-5">
                    <a class="navbar-brand" >Project Vuejs</a>
                    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation"><span class="navbar-toggler-icon"></span></button>
                    <div class="collapse navbar-collapse" id="navbarSupportedContent">
                        <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                            <li class="nav-item"><router-link class="nav-link text-primary" to="/"><i class="fas fa-home"></i> Home (หน้าหลัก)</router-link></li>
                            <li class="nav-item"><router-link class="nav-link text-warning" to="/product"><i class="fas fa-store"></i> Product (สินค้าและบริการ)</router-link></li>
                            <li class="nav-item mr-5"><a class="nav-link" href="#">Contact</a></li>
                            <li class="nav-item mr-3"><router-link class="btn btn-primary btn-index" to="/login">เข้าสู่ระบบ</router-link></li>
                            <li class="nav-item"><router-link class="btn btn-warning" to="/reg">สมัครสมาชิก</router-link></li>
                        </ul>
                    </div>
                </div>
            </nav>
            <!-- Header-->
            <header class="header py-5 ">
                <div class="container px-5 ">
                    <div class="row">
                        <div v-for="value in product" v-bind:key="value" class="col-md-4" >
                            <div class="card" style="width: 20rem;">
                                <img :src="value.pro_img" style="width:100%;" alt="">
                            <div class="card-body">
                                    <h5 class="card-title text-danger">{{ value.pro_name }}</h5>
                                    <p class="card-text">ราคา {{ value.pro_price }} บาท</p>
                                    <p class="card-text">คงเหลือ {{ value.pro_item }} ชิ้น</p>
                                    <a href="#" class="btn btn-primary mr-2"><i class="fas fa-cart-plus"></i> สั่งซื้อ</a>
                                    <router-link class="btn btn-secondary" to="/detail"><i class="fas fa-info"></i> รายละเอียด</router-link>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
            </header>
        </main>
</template>
<script>
import axios from "axios";
export default {

  name: "App",
  components: {},
  data() {
    return {
      product: [],
    };
  },
  mounted () {
      axios.get("http://localhost:7777/showproduct", {
        headers: {
          "Content-Type": "application/json",
        },
      })
      .then((response) => {
        console.log(response);
        console.log(response.data);
        this.product = response.data;
      })
      .catch(function (error) {
        console.log(error);
      });
  },
};
</script>