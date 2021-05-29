<template>
  <div class="partners mt-5 " id="support">
    <ul
      class="row justify-content-around align-item-center mx-5 my-5 p-5 list-unstyled"
    >
      <li
        class="col-md-3 mt-md-4 "
      >
        <img
          src="../assets/image/suretkargo.png"
          alt=""
          class="img-fluid"
        />
      </li>
      <li
        class="col-md-3 ml-md-5 pl-md-5 my-md-0 my-5"
      >
        <img
          src="../assets/image/bringly.svg"
          alt=""
          class="img-fluid"
        />
      </li>
      <li
        class="col-md-3  mx-4"
      >
        <img
          src="../assets/image/starex.png"
          alt=""
          class="img-fluid"
        />
      </li>
      
    </ul>
    <button class="right">
      <i class="fas fa-arrow-right" @click="slideRight"></i>
    </button>
    <button class="left">
      <i class="fas fa-arrow-left" @click="slideLeft"></i>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      direction: "",
      currentIndex: 0,
      partners: ["suretkargo.png", "bringly.svg", "starex.png"],
    };
  },
  methods: {
    slideLeft() {
      this.currentIndex--;
      if (this.currentIndex < 0) {
        this.currentIndex = this.partners.length - 1;
      }
    },
    slideRight() {
      this.currentIndex++;
      if (this.currentIndex > this.partners.length - 1) {
        this.currentIndex = 0;
      }
    },
  },
};
</script>

<style scoped>
li:first-child {
  padding-top: 20px;
}

.partners {
  position: relative;
}

.right {
  position: absolute;
  top: 45%;
  right: 5%;
}
.left {
  position: absolute;
  top: 45%;
  left: 5%;
}
.col-md-5 img {
  margin-left: 50%;
  transform: translate(-50%);
}
.partners::before {
  content: "Partners";
  position: absolute;
  font-size: 30px;
  font-weight: 900;
  top: 10%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.change-enter-active {
  animation: animate 0.5s linear;
}
.change-enter-active {
  animation: animate 0.5s linear reverse;
}

@keyframes animate {
  0% {
    opacity: 2;
  }

  100% {
    opacity: 0;
  }
}

@media screen and (max-width: 768px) {
  .partners::before {
    font-size: 20px;
  }
}
</style>
