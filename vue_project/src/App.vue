<template>
  <div id="">
    <router-view/>
  </div>
</template>

<style>
.swal2-popup {
  font-family: 'Mitr', sans-serif !important;
}
.header{
  background-image: url("https://cdn.pixabay.com/photo/2016/11/30/20/58/programming-1873854_960_720.png");
  display: flex;
  height: 92vh;
}
#navbarSupportedContent{
  margin-right: -100px;
}
.navbar-brand{
  margin-left: -100px;
}
#home,.login-page,.register-page{
  font-family: 'Mitr', sans-serif;
}
.login-box{
  width: 400px;
}
.register-box{
  width: 600px;
}
.login-page,.register-page{
  background-image: url("https://cdn.pixabay.com/photo/2016/11/19/14/00/code-1839406_960_720.jpg");
}
#app {
  font-family: 'Mitr', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-image: url("https://cdn.pixabay.com/photo/2016/11/19/14/00/code-1839406_960_720.jpg");
  
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
