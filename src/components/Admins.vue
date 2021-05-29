<template>
  <li class="my-5 admin py-5">
    <div v-for="(user, index) in featuresUsers" :key="index">
      <div class="col-md-7" v-if="currentIndex == index">
        <img src="../assets/featuresAdmin.svg" alt="" />
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
        <h3 class="text-primary ">
          <img src="../assets/Ellipse.svg" alt="" />
          {{ user.name  }} 
          
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
            name="slide2"
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
          name: "Sms Section",
          img: "adminimg1",
          sections: [
            "- Section for managing the content of the site (news, pages, FAQ)",
          ],
        },
        {
          name: "Balance",
          img: "adminimg2",
          sections: [
            "- Virtual wallets of users of different currencies - balances (TL, USD)",
            "- Balance control mechanism (detailed effect of the reasons for payments - debit, credit)",
          ],
        },
        {
          name: "Warehouse Managment",
          img: "adminimg3",
          sections: [
            "- Warehouse management of incoming products",
            "- The mechanism of optimal placement of products on the shelves",
            "- Manage warehouse operations with a special android app",
            "- Multi-country warehouse system capability (TR - AZ, USA - AZ, DE - TR, UAE - TR, DE - AZ)",
            "- Possibility to increase Local Warehouses (Baku 1, Baku 2, Ganja, Lankaran, etc.)",
          ],
        },
        {
          name: "Order",
          img: "adminimg4",
          sections: ["- Control all sent links in admin panel"],
        },
        {
          name: "Paydesk",
          img: "adminimg5",
          sections: [
            "- The operation of those who come to pick up their products is carried out here",
            "- Offline account - functionality of depositing money from the office",
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
  display: inline;
}
.admin{
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
.admin::before {
  content: "Features for Admin";
  font-size: 30px;
  font-weight: 900;
  position: absolute;
  left: 50%;
  bottom: 110%;
  transform: translate(-50%, 50%);
}

.col-md-7 {
  position: relative;
}
.img1 {
  position: absolute;
  left: 15%;
  top: 15%;
  width: 80%;
}

.col-md-7 img:first-child {
  width: 100%;
  height: 500px;
}

button {
  border-radius: 50%;
}


h3 img{
    position: absolute;
    top: -25px;
    left: -15px;
    z-index: -100;
    width: 80px !important;
}

@media screen and (max-width: 768px) {
  h3 {
    width: 180px;
    margin-left: 55%;
    transform: translate(-50%);
    text-align: left;
  }
  
  .img1{
    top: 30%;
  }
  .admin::before {
    content: "Features for admin";
    font-size: 15px;
    font-weight: 900;
    position: absolute;
    left: 50%;
    bottom: 110%;
    transform: translate(-50%, 50%);
  }
}
</style>
