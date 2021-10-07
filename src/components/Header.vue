<template>
  <header class="header">
    <a href="#" class="logo">
      <img src="@/assets/images/logo.png" alt="" />
    </a>

    <!-- <nav class="navbar"> -->
    <nav :class="{ navbar: navbarClass, 'navbar active': !navbarClass }">
      <a href="#home">home</a>
      <a href="#about">about</a>
      <a href="#menu">menu</a>
      <a href="#products">products</a>
      <a href="#review">review</a>
      <a href="#contact">contact</a>
      <a href="#blogs">blogs</a>
    </nav>

    <div class="icons">
      <!-- <div class="fas fa-search" id="search-btn" @click="search"></div> -->
      <div
        :class="{
          'fas fa-search': searchIconClass,
          'fas fa-times': !searchIconClass,
        }"
        id="search-btn"
        @click="search"
      ></div>
      <div class="fas fa-shopping-cart" id="cart-btn" @click="cart"></div>
      <!-- <div class="fas fa-bars" id="menu-btn"></div> -->
      <div
        :class="{ 'fas fa-bars': menuClass, 'fas fa-times': !menuClass }"
        @click="menu"
        id="menu-btn"
      ></div>
    </div>

    <!-- <div class="search-form"> -->
    <div
      :class="{
        'search-form': searchFormClass,
        'search-form active': !searchFormClass,
      }"
    >
      <input type="search" id="search-box" placeholder="search here..." />
      <!-- <label for="search-box" class="fas fa-search"></label> -->
      <label
        for="search-box"
        :class="{
          'fas fa-search': searchIconClass,
          'fas fa-times': !searchIconClass,
        }"
        @click="search"
      ></label>
    </div>

    <div
      :class="{
        'cart-items-container': cartItem,
        'cart-items-container active': !cartItem,
      }"
    >
      <div class="cart-item">
        <span class="fas fa-times"></span>
        <img src="@/assets/images/cart-item-1.png" alt="" />
        <div class="content">
          <h3>cart item 01</h3>
          <div class="price">$15.99/-</div>
        </div>
      </div>
      <div class="cart-item">
        <span class="fas fa-times"></span>
        <img src="@/assets/images/cart-item-2.png" alt="" />
        <div class="content">
          <h3>cart item 02</h3>
          <div class="price">$15.99/-</div>
        </div>
      </div>
      <div class="cart-item">
        <span class="fas fa-times"></span>
        <img src="@/assets/images/cart-item-3.png" alt="" />
        <div class="content">
          <h3>cart item 03</h3>
          <div class="price">$15.99/-</div>
        </div>
      </div>
      <div class="cart-item">
        <span class="fas fa-times"></span>
        <img src="@/assets/images/cart-item-4.png" alt="" />
        <div class="content">
          <h3>cart item 04</h3>
          <div class="price">$15.99/-</div>
        </div>
      </div>
      <a href="#" class="btn">checkout now</a>
    </div>
  </header>
</template>
<script>
export default {
  data() {
    return {
      menuClass: true,
      navbarClass: true,
      searchIconClass: true,
      searchFormClass: true,
      cartItem: true,
    };
  },
  created: function() {
    window.addEventListener("scroll", this.handleScroll);
  },
  unmounted: function() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    menu() {
      // alert("menu clicked");
      this.menuClass = !this.menuClass;
      this.navbarClass = !this.navbarClass;
      this.searchIconClass = true;
      this.searchFormClass = true;
      this.cartItem = true;
    },
    search() {
      // alert("search clicked");
      this.searchIconClass = !this.searchIconClass;
      this.searchFormClass = !this.searchFormClass;
      this.menuClass = true;
      this.navbarClass = true;
      this.cartItem = true;
    },
    cart() {
      this.cartItem = !this.cartItem;
      this.menuClass = true;
      this.navbarClass = true;
      this.searchIconClass = true;
      this.searchFormClass = true;
    },
    handleScroll() {
      this.menuClass = true;
      this.navbarClass = true;
      this.searchIconClass = true;
    },
  },
};
</script>
