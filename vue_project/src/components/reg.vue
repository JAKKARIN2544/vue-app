<template>
    <body class="hold-transition register-page">
<div class="register-box">
  <div class="card card-outline">
    <div class="card-header text-center">
      <router-link class="h1" to="/"><b class="text-success">Vue</b> ProJect</router-link>
    </div>
    <div class="card-body">
      <p class="login-box-msg">สมัครสมาชิกก่อนเข้าใช้งาน</p>
        <div class="input-group mb-3">
          <input type="text" class="form-control" placeholder="Frist name" v-model="fName">
          <div class="input-group-append mr-3">
            <div class="input-group-text">
              <span class="fas fa-user"></span>
            </div>
          </div>
          <input type="text" class="form-control" placeholder="Last name" v-model="lName">
          <div class="input-group-append">
            <div class="input-group-text">
              <span class="fas fa-user"></span>
            </div>
          </div>
        </div>
        <div class="input-group mb-3">
          <input type="email" class="form-control" placeholder="Email" v-model="Email">
          <div class="input-group-append">
            <div class="input-group-text">
              <span class="fas fa-envelope"></span>
            </div>
          </div>
        </div>
        <div class="input-group mb-3">
          <input type="password" class="form-control" placeholder="Password" v-model="Password">
          <div class="input-group-append">
            <div class="input-group-text">
              <span class="fas fa-lock"></span>
            </div>
          </div>
        </div>
        <div class="input-group mb-3">
          <input type="text" class="form-control" placeholder="phone" v-model="Phone">
          <div class="input-group-append">
            <div class="input-group-text">
              <span class="fas fa-phone"></span>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-8">
            <div class="icheck-primary">
              <input type="checkbox" id="agreeTerms" name="terms" value="agree">
              <label for="agreeTerms">
               ยอมรับ <a href="#">ข้อตกลง</a>
              </label>
            </div>
          </div>
          <!-- /.col -->
          <!-- /.col -->
        </div>
        <div class="row">
            <div class="col-md-4"></div>
            <div class="col-md-3"></div>
      <div class="social-auth-links text-center">
        <button  class="btn btn-block btn-primary" @click="Register">
          <i class="fas fa-user mr-2"></i>
          สมัครสมาชิก
        </button>
      </div>
            <div class="col-md-4"></div>
        </div>
      <router-link class="text-center" to="/login">มีสมาชิกอยู่แล้ว </router-link>
    </div>
    <!-- /.form-box -->
  </div><!-- /.card -->
</div>
<!-- /.register-box -->
</body>
</template>
<script>
import axios from 'axios';
import Swal from 'sweetalert2';
    export default {
        name:"App",
        components:{},
        data(){
            return{
                fName:"",
                lName:"",
                Phone:"",
                Email:"",
                Password:"",
               
            };
        },
        methods:{
            Register(){
                console.log(this.fName)
                console.log(this.lName)
                console.log(this.Phone)
                console.log(this.Email)
                console.log(this.Password)
                axios.get("http://localhost:7777/insertData", {
                params:{
                    fName: this.fName,
                    lName: this.lName,
                    Phone: this.Phone,
                    Email: this.Email,
                    Password: this.Password,
                },
            headers: {
            "Content-Type": "application/json",
            }
        })
        .then((response) => {
            // this.datas = response.data
            console.log(response);
            console.log(response.data);
                Swal.fire({
                    icon: 'success',
                    title: 'สำเร็จ',
                    text: 'สมัครสมาชิก สำเร็จ',
                    timer: 1500
                });
                this.fName = "",
                this.lName = "",
                this.Phone = "",
                this.Email = "",
                this.Password = "";
                this.$router.push('/login');

        })
       .catch(function (error) {
             console.log(error);
                Swal.fire({
                    icon: 'error',
                    title: 'คำเตือน...',
                    text: '!!!!',
                    timer: 1500
                });
        });
            }
        },
    }
</script>