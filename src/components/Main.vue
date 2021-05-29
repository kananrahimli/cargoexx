<template>
  <div class="main mb-5">
    <div class="py-5">
      <ul class=" list-unstyled row justify-content-around">
        <li class="col-md-3 my-5 text-center">
          <img src="../assets/Watch.svg" alt="" />
        </li>
        <li class="col-md-3 my-5 text-center">
          <img src="../assets/cubics.svg" alt="" />
        </li>
        <li class="col-md-3 my-5 text-center">
          <img src="../assets/person.svg" alt="" />
        </li>
      </ul>
    </div>

    <div class="main-section"  id="features">
      <ul class="row">
          
          <Users/>
          
          <Admins/>
      </ul>
    </div>
  </div>
</template>

<script>
import Users from './Users.vue'
import Admins from './Admins.vue'
export default {
  components:{
    Users,
    Admins
  },
  data() {
    return {
      
    };
  },
};
</script>

<style scoped>


.main {
  margin-top: 350px;
}


.main-section {
  margin-top: 150px;
}
 


@media screen and (max-width: 768px) {
  .main {
    margin-top: 250px;
  }
   
}

@media screen and (max-width: 425px) {
  .main {
    margin-top: 150px;
  }
}
</style>
