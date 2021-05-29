<template>
  <header class="d-flex justify-content-center align-items-center" id="home">
    <div class="navigation position-fixed w-100  " >
      <div class="nav-logo pb-3">
        <a href="" class="link"><img src="../assets/Frame.svg" alt=""></a>
      </div>
      <ul class="nav-list">
        <li class="nav-item"><a href="#home" class="link"> Home</a></li>
        <li class="nav-item"><a href="#features" class="link"> Features</a></li>
        <li class="nav-item"><a href="#support" class="link"> Support</a></li>
        <li class="nav-item"><a href="#contact" class="link"> Contact</a></li>
      </ul>
      <div class="request-button">
        <button class="">Request</button>
      </div>
      <div class="menubar">
        <button>
          <transition name="buttons" tag="button">
          <i class="fas fa-bars" @click="open" v-if="!isBool"></i>
        </transition>
        <transition name="buttons" tag="button">
          <i class="fas fa-times" @click="close" v-if="isBool"></i>
        </transition>
        </button>
        
      </div>
    </div>
    <div class="header-text">
      <h5 class="text-light text-center">
        Cargo-ex aims to help users to bring products
ordered from foreign countries (Turkey, America and etc. ) to them.
      </h5>
    </div>
  </header>
</template>

<script>
export default {
  props:['isBool'],
  data() {
    return {
      
    };
  },
  methods: {
    open() {
      
      this.$emit('open')
    },
    close() {
      
      this.$emit('close')
    },
  },
  emits:['open','close']
};
</script>

<style scoped>


h5{
  font-size: 30px;
  font-weight: 900;
}
.menubar {
  display: none;
}
header {
  background-image: url("../assets/image/MaskGroup.jpg");
  /* background-attachment: fixed; */
  background-size: cover;
  background-position: center;
  height: 85vh;
  overflow: hidden;
  position: relative;
}
.header-text {
  padding:0 100px;
}

.navigation {
  display: flex;
  justify-content: space-around;
  padding-top: 20px;
  background: #fff;
  z-index: 100;
  top: 0;
}

.nav-list {
  display: flex;
  list-style: none;
}
.nav-item {
  margin: 0 20px;
}

.request-button{
  border: 1px solid #007bff;
  align-self: baseline;
  margin-bottom: 10px;
  padding: 3px 10px;
  border-radius: 20px;
  transition: 0.5s;
}
.request-button:hover{
  background-color:#007bff;
  color: white;
}

.link{
  text-decoration: none;
  transition: 0.5s;
}

.link:hover{
  color: rgb(146, 196, 72);
}

/* responsive */
@media screen and (max-width: 768px) {
  .nav-list {
    display: none !important;
  }
  .header-text {
    padding: 0 20px !important;
  }
  .menubar {
    display: block;
  }
  .request-button{
    display: none;
  }
  h5{
  font-size: 20px;
  font-weight: 900;
}
}

.buttons-enter-active {
  animation: animate 0.3s linear;
}

.buttons-leave-active {
  animation: animate 0.1s ease-in reverse;
}

@keyframes animate {
  0% {
    opacity: 0;
  }

  
  100% {
    opacity: 1;
  }
}
</style>
