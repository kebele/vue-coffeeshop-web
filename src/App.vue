<template>
  <div>
    <Header />
    <Home />
    <About />
    <Menu />
    <Products />
    <Review />
    <Contact />
    <Blog />
    <Footer />
  </div>
</template>

<script>
// import Header from "./components/Header.vue";
import Home from "./components/Home.vue";
import About from "./components/About.vue";
import Menu from "./components/Menu.vue";
import Products from "./components/Products.vue";
import Review from "./components/Review.vue";
import Contact from "./components/Contact.vue";
import Blog from "./components/Blog.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    // Header,
    Home,
    About,
    Menu,
    Products,
    Review,
    Contact,
    Blog,
    Footer,
  },
};
</script>

<style></style>
