<template>
<div class="parent-container">
  <nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <a class="navbar-item" href="https://bulma.io">
      <img src="https://bulma.io/images/bulma-logo.png" width="112" height="28">
    </a>

    <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
    </a>
  </div>

  <div id="navbarBasicExample" class="navbar-menu">
    <div class="navbar-start">
      <a class="navbar-item">
        Home
      </a>

      <a class="navbar-item">
        Documentation
      </a>

      <div class="navbar-item has-dropdown is-hoverable">
        <a class="navbar-link">
          More
        </a>

        <div class="navbar-dropdown">
          <a class="navbar-item">
            About
          </a>
          <a class="navbar-item">
            Jobs
          </a>
          <a class="navbar-item">
            Contact
          </a>
          <hr class="navbar-divider">
          <a class="navbar-item">
            Report an issue
          </a>
        </div>
      </div>
    </div>

    <div class="navbar-end">
      <div class="navbar-item">
        <div class="buttons">
          <a class="button is-primary">
            <strong>Sign up</strong>
          </a>
          <a class="button is-light">
            Log in
          </a>
        </div>
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

</script>


<style scoped>
    .parent-container{
      width: 100%;
      background-image: linear-gradient(to right top, #e8c083, #e9c795, #e9cea7, #e9d5ba, #e8dccc);
    }
    .navbar{
        background: transparent;
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
      font-size: 35px;
      font-weight: 800;
    }
    .title p{
      font-weight: 700;
      color: var(--dark-grey);
      margin-top: 8px;
    }
    
</style>