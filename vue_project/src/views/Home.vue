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
                    <div class="row gx-5 align-items-center justify-content-center ">
                        <div class="col-lg-8 col-xl-7 col-xxl-6">
                            <div class="my-5 text-center text-xl-start">
                                <h1 class="display-5 fw-bolder text-white mb-2">A Bootstrap 5 template for modern businesses</h1>
                                <p class="lead fw-normal text-white-50 mb-4">Quickly design and customize responsive mobile-first sites with Bootstrap, the world’s most popular front-end open source toolkit!</p>
                                <div class="d-grid gap-3 d-sm-flex justify-content-sm-center justify-content-xl-start">
                                    <a class="btn btn-primary btn-lg px-4 me-sm-3" href="#features">Get Started</a>
                                    <a class="btn btn-outline-light btn-lg px-4" href="#!">Learn More</a>
                                </div>
                            </div>
                        </div>
                        <div class="col-xl-5 col-xxl-6 d-none d-xl-block text-center"><img class="img-fluid rounded-3" src="https://pngimg.com/uploads/hacker/hacker_PNG33.png" alt="..." /></div>
                    </div>
                </div>
                <br>
                <br>
            </header>
        </main>
        
</template>

<script>
// @ is an alias to /src
export default {
  name: 'Home',
  components: {
    
  },
}

</script>
