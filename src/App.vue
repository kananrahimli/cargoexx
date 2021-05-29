<template>
  <div id="app">
    <Header @open="openMenu" @close="closeMenu" :isBool="isBool"/>
    <Carousel />
    <Main />
    <Contact />
    <partners></partners>
    <Mobile :isBool="isBool" @close="closeMenu"></Mobile>
    <Footer/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Carousel from "./components/Carousel.vue";
import Main from "./components/Main.vue";
import Contact from "./components/Contact.vue";
import Partners from "./components/Partners.vue";
import Mobile from "./components/Mobile.vue";
import Footer from './components/Footer.vue'
export default {
  name: "App",
  components: {
    Header,
    Carousel,
    Main,
    Contact,
    Partners,
    Mobile,
    Footer
  },
  data(){
    return{
      isBool:false
    }
  },
  methods:{
    openMenu(){
      this.isBool=true
    },
    closeMenu(){
      this.isBool=false 
    }
  }
};
</script>

<style scoped >
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  overflow: hidden;
}

html{
  scroll-behavior: smooth;
}


</style>
