<template>
<div class="parent-container">
  <nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <a class="navbar-item" href="#">
      <img src="@/assets/restaurant.png" width="40" height="28">
    </a>

    <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navMenu" @click="makeBurger">
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
    </a>
  </div>

  <div id="navMenu" class="navbar-menu" :class="{ 'is-active': activator }">

    <div class="navbar-end">
      <div class="navbar-item">
          <a class="" href="#location">
            Ubicación
          </a>
          <a class="" href="#menu">
            Menú
          </a>
          <a class="" href="#shopping">
            Tu compra
          </a>
          <a class="" href="#contact">
            Contacto
          </a>
      </div>
    </div>
  </div>
</nav>
    <div class="header-container">
        <div class="header-img"></div>
        <div class="title">
            <h1>Como en casa</h1>
            <p>Restaurante</p>
        </div>
    </div>
</div>

    
</template>

<script>
  export default{
    name: 'Navbar',
    data () {
      return {
        msg: '',
        activator: false
      }
    },
    methods: {
      makeBurger () {
        this.activator = !this.activator
        return this.activator
      }
    }
  }
</script>


<style scoped>
    .parent-container{
      width: 100%;
      background-image: linear-gradient(to right top, #e8c083, #e9c795, #e9cea7, #e9d5ba, #e8dccc);
    }
    .navbar{
        background: transparent;
    }
    .navbar-brand{
      padding-left: 10px;
    }
    .header-container{
        width: 100%;
        height: 400px;
        
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .header-img{
      background-image: url(@/assets/header.jpg);
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;
      width: 200px;
      height: 200px;
      border-radius: 50%;
      box-shadow: 0px -1px 10px 4px var(--orange);
    }
    .title{
      margin-top: 35px;
      
    }
    .title h1{
      font-family: 'Open Sans', sans-serif;
      color: #fff;
      font-size: 45px;
      font-weight: 800;
    }
    .title p{
      font-weight: 700;
      color: var(--dark-grey);
      margin-top: 8px;
    }
    .navbar-item a{
      margin: 5px;
      color: var(--dark-grey);
      font-weight: 700;
    }
    .navbar-item a:hover{
      color: var(--orange);
      transition: color 0.4s;
    }
    .navbar-item{
      padding: 0;
    }
    .is-active .navbar-item{
      display: flex;
      flex-direction: column;
      background-color: var(--dark-beige);
      padding-top: 0;
    }
    @media (min-width: 1024px) {
      .navbar-end{
        padding-right: 10px;
      }
    }
</style>