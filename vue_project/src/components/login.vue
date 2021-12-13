<template>
    <body class="hold-transition login-page">
<div class="login-box">
  <!-- /.login-logo -->
  <div class="card card-outline">
    <div class="card-header text-center">
      <router-link class="h1" to="/"><b class="text-success">Vue</b> ProJect</router-link>
    </div>
    <div class="card-body">
      <p class="login-box-msg">Sign in ก่อนเข้าสู่ระบบ</p>
        <div class="input-group mb-3">
          <input v-model="Email" type="email" class="form-control" placeholder="Email">
          <div class="input-group-append">
            <div class="input-group-text">
              <span class="fas fa-envelope"></span>
            </div>
          </div>
        </div>
        <div class="input-group mb-3">
          <input v-model="Password" type="password" class="form-control" placeholder="Password">
          <div class="input-group-append">
            <div class="input-group-text">
              <span class="fas fa-lock"></span>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-8">
            <div class="icheck-primary">
              <input type="checkbox" id="remember">
              <label for="remember">
                จดจำผู้ใช้งาน
              </label>
            </div>
          </div>
          <!-- /.col 
          <div class="col-4">
            <button type="submit" class="btn btn-primary btn-block">ล็อกอิน</button>
          </div>
           /.col -->
        </div>

      <div class="social-auth-links text-center mt-2 mb-3">
        <button class="btn btn-block btn-success" @click="Login">
          <i class="fas fa-sign-in-alt mr-2"></i> เข้าสู่ระบบ
        </button>
      </div>
      <!-- /.social-auth-links -->

      <router-link class="mb-1" to="/">
        <a >ลืมรหัสผ่าน ???</a>
      </router-link>
      <p class="mb-0">
        <router-link  class="text-center text-black" to="/reg">สมัครสมาชิก <span class="text-danger">คลิ๊ก</span></router-link>
      </p>
    </div>
    <!-- /.card-body -->
  </div>
  <!-- /.card -->
</div>
<!-- /.login-box -->
</body>
</template>
<script>
import axios from 'axios';
import Swal from 'sweetalert2';
export default {
    name: "Login",
    components: {},
    data() {
        return{
            Email:"",
            Password:"",
        };
    },
    methods: {
        Login(){
            axios.get("http://localhost:7777/Datalogin", {
                params:{
                    Email: this.Email,
                    Password: this.Password,
                },
            headers: {
            "Content-Type": "application/json",
            }
        })
        .then((response) => {
            // this.datas = response.data
            console.log(response.data);
            if(response.data.data.length > 0){
                Swal.fire({
                    icon: 'success',
                    title: 'สำเร็จ',
                    text: 'เข้าสู่ระบบ สำเร็จ',
                    timer: 1500
                });
                this.$router.push('/');
            }else{
                Swal.fire({
                    icon: 'error',
                    title: 'คำเตือน...',
                    text: 'กรอกรหัสให้ถูกดิไอ้เวร!!!!',
                    timer: 1500
                });
            }
        })
       .catch(function (error) {
             console.log(error);
        });
        },
    },
};
</script>