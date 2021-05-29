<template>
  <li class="my-5 user py-5">
    <div v-for="(user, index) in featuresUsers" :key="index">
      <div class="col-md-7" v-if="currentIndex == index">
        <img src="../assets/featuresUsers.svg" alt="" />
        <img
          :src="require('../assets/image/' + user.img + '.jpg')"
          alt=""
          class="img1"
        />
      </div>

      <div
        class="col-md-3 d-flex flex-column mt-5 pt-4 text-md-left text-center "
        v-if="currentIndex == index"
      >
        <h3 class="text-primary">
          {{ user.name }}
          <img src="../assets/Ellipse.svg" alt="" />
        </h3>
        
        <ul
          class="list-unstyled d-flex flex-column mt-3  font-weight-bold"
          v-for="section in user.sections"
          :key="section"
        >
          <li>{{ section }}</li>
        </ul>
      </div>

      <div
        class="col-md-2  d-flex justify-content-around p-5 mt-4"
        v-if="currentIndex == index"
      >
        <div class="action d-flex flex-column justify-content-center mb-2 pt-5">
          <button
            class="right btn btn-outline-primary mt-2"
            @click="slideRight"
          >
            <i class="fas fa-arrow-right "></i>
          </button>
          <button class="left btn btn-outline-primary mt-2" @click="slideLeft">
            <i class="fas fa-arrow-left"></i>
          </button>
        </div>
        <div class="radios flex-column  d-flex pt-5">
          <input
            type="radio"
            class="mt-1"
            name="slide1"
            v-for="(user, index) in featuresUsers"
            :key="index"
            :value="index"
            v-model="radioValue"
            @input="currentIndex = index"
          />
        </div>
      </div>
    </div>
  </li>
</template>

<script>
export default {
  data() {
    return {
      radioValue: 0,
      currentIndex: 0,
      featuresUsers: [
        {
          name: "User System",
          img: "userimg1",
          sections: [
            "- User sign-up",
            "- Personal cabinet",
            "- Password recovery ",
          ],
        },
        {
          name: "Balance",
          img: "userimg2",
          sections: [
            "- Virtual wallets of users of different currencies - balances (TL, USD)",
            "- Purchase amount during the last 30 days",
            "- Ability to increase your balance online and with paypoints",
          ],
        },
        {
          name: "Declare",
          img: "userimg3",
          sections: [
            "- Users fill out a declaration according to their orders",
          ],
        },
        {
          name: "Order",
          img: "userimg4",
          sections: [
            "- Instruct users to get the links they want from the company. Write the parameters in the link and submit it for purchase",
            "- Interest calculation and payments for links",
            "- Tracking link purchase statuses",
          ],
        },
        {
          name: "Tracking packages",
          img: "userimg5",
          sections: [
            "- Ability to follow the statements of users and their links to the links ordered by the Order service",
            "- Monitoring the status of the package",
            "- Application of a penalty mechanism to ensure that parcels do not remain in excessive storage",
          ],
        },
        {
          name: "Warehouse Managment",
          img: "userimg6",
          sections: [
            "- Multi-country warehouse system capability (TR - AZ, USA - AZ, DE - TR, UAE - TR, DE - AZ)",
            "- Possibility to increase Local Warehouses (Baku 1, Baku 2, Ganja, Lankaran, etc.)",
          ],
        },
      ],
    };
  },

  methods: {
    slideLeft() {
      this.currentIndex = this.currentIndex - 1;
      this.radioValue--;
      if (this.currentIndex < 0) {
        this.currentIndex = this.featuresUsers.length - 1;
        this.radioValue = this.featuresUsers.length - 1;
      }
    },
    slideRight() {
      this.currentIndex++;
      this.radioValue++;
      if (this.currentIndex == this.featuresUsers.length) {
        this.currentIndex = 0;
        this.radioValue = 0;
      }
    },
  },
};
</script>

<style scoped>

h3 {
  font-size: 30px;
  position: relative;
}

li {
  position: relative;
}
li:nth-child(even) div {
  float: right;
}
li:nth-child(odd) div {
  float: left;
}
li:nth-child(odd) .action {
  order: 2;
}
.user::before {
  content: "Features for Users";
  font-size: 30px;
  font-weight: 900;
  position: absolute;
  left: 50%;
  bottom: 120%;
  transform: translate(-50%, 50%);
}

/* li img {
  width: 25%;
} */

.col-md-7 {
  position: relative;
}
.img1 {
  position: absolute;
  left: 8%;
  top: 10%;
  width: 80%;
}

 h3 img {
  position: absolute;
    top: -25px;
    left: -15px;
    z-index: -100;
    width: 80px !important;
}

button {
  border-radius: 50%;
}

.col-md-7 img:first-child {
  width: 100%;
}

@media screen and (max-width: 768px) {
  h3 {
    width: 180px;
    margin-left: 55%;
    transform: translate(-50%);
    text-align: left;
  }
  
  .user::before {
    content: "Features for Users";
    font-size: 15px;
    font-weight: 900;
    position: absolute;
    left: 50%;
    bottom: 110%;
    transform: translate(-50%, 50%);
  }
}

@media screen and (max-width: 425px) {
  .main {
    margin-top: 150px;
  }
}
</style>
