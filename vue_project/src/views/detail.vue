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
                            <li class="nav-item"><router-link class="nav-link" to=""><i class="fas fa-shopping-basket"></i> ตะกร้าสินค้าของฉัน</router-link></li>
                            <li class="nav-item mr-3"><router-link class="btn btn-primary btn-index" to="/login">เข้าสู่ระบบ</router-link></li>
                            <li class="nav-item"><router-link class="btn btn-warning" to="/reg">สมัครสมาชิก</router-link></li>
                        </ul>
                    </div>
                </div>
            </nav>
            <!-- Header-->
            <header class="header py-5 ">
                <div class="container px-5 ">
                    <div v-for="Product in Product" :key="Product.id" class="row bg-white mb-5 mt-4" >
                        <div class="col-12 col-sm-6">
                           
                            <div class="col-12 mt-5">
                              <img :src="Product.pro_img" style="width:500px;" class="product-image" alt="">
                            </div>
                          </div>
                          <div class="col-12 col-sm-6">
                          <h1 class="my-3"> {{ Product.pro_name }} </h1>
                          <hr>
                            <h4>รายละเอียดสินค้า</h4>
                              <p>{{ Product.pro_detail }}</p>
                              <h4>สินค้าคงเหลือ</h4>
                              <p>{{Product.pro_item }} ชิ้น</p>
                          <div class=" py-2 px-3 mt-4">
                            <h2 class="mb-0">
                                ราคา <span class="text-danger">{{Product.pro_price }}</span> บาท
                            </h2>
                          </div>

                          <div class="mt-4 mb-4 ">
                            <div class="btn btn-primary btn-lg mr-5">
                              <i class="fas fa-cart-plus fa-lg mr-2"></i>
                              สั่งซื้อสินค้า
                            </div>
                            <router-link class="btn btn-secondary btn-lg" to="/product">
                              <i class="fas fa-backward mr-2"></i>
                              ย้อนกลับ
                            </router-link>
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
      
      Product: [],
    };
  },
  mounted () {
      axios.get("http://localhost:7777/DetailProduct", {
        params: {
         id: this.$route.params.pro_id,
         },
        headers: {
          "Content-Type": "application/json",
        },
      })
      .then((response) => {
        //console.log(response);
        console.log(response.data.data);
        this.Product = response.data.data;
      })
      .catch(function (error) {
        console.log(error);
      });
  }
}
</script>