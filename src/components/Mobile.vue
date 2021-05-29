<template>
  <transition name="mobileNav">
    <div
      class="mobile-nav w-50 d-flex flex-column align-items-center justify-content-around"
      v-if="isBool"
    >
      <ul
        class="d-flex flex-column align-items-center justify-content-around list-unstyled mt-5"
      >
        <li class="my-3" v-for="(lnk,index) in links"
            :key="index">
          <a
            :href="lnk.href"
            class="link"
            
            @click="$emit('close')"
            >{{ lnk.link }}</a
          >
        </li>
      </ul>

      <div class="request-button mt-5">
        <button>Request</button>
      </div>

      <span class="d-bolck text-primary"
        >Designed by:<span class="text-dark">Labrin</span></span
      >
    </div>
  </transition>
</template>

<script>
export default {
  props: ["isBool"],
  emits: ["close"],
  data() {
    return {
      links: [
        {link:'Home',href:'#home'},
         {link:'Features',href:'#features'},
          {link:'Support',href:'#support'},
           {link:'Contact',href:'#contact'}
      ],
    };
  },
};
</script>

<style scoped>

.mobile-nav {
  display: none;
  box-shadow: 5px 0px 8px rgba(0, 0, 0, 0.4);
  opacity: 0.9;
}

.request-button {
  border: 1px solid #007bff;
  margin-bottom: 10px;
  padding: 3px 10px;
  border-radius: 20px;
  transition: 0.5s;
}

.request-button:hover {
  background-color: #007bff;
  color: white;
}

.link {
  text-decoration: none;
  transition: 0.5s;
}

.link:hover {
  color: rgb(146, 196, 72);
}

@media screen and (max-width: 768px) {
  .mobile-nav {
    display: block;
    background-color: #fff;
    height: 100vh;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 100;
  }
}

.mobileNav-enter-active {
  animation: showMobileMenu 0.5s linear;
}
.mobileNav-leave-active {
  animation: showMobileMenu 0.5s linear reverse;
}

@keyframes showMobileMenu {
  0% {
    transform: translateX(-100px);
  }

  50% {
    transform: translateX(100px);
  }

  100% {
    transform: translateX(0px);
  }
}
</style>
