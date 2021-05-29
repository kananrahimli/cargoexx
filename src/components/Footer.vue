<template>
  <div>
    <div class="footer p-5">
      <div class="d-flex flex-column align-items-center ">
        <ul
          class="d-flex list-unstyled font-weight-bold justify-content-around px-5 mx-auto w-100 flex-wrap"
        >
          <li>
            <a href="">Home</a>
          </li>
          <li>
            <a href="">Features</a>
          </li>
          <li>
            <a href="">Contact</a>
          </li>
        </ul>

        <div class=" mt-5">
          <img src="../assets/Frame.svg" alt="" />
        </div>
      </div>
    </div>
    <div class="py-3 px-5 d-flex justify-content-between">
        <h5 class="text-primary mt-1">Cargoex {{getYear}}</h5>
         <span class="d-bolck text-primary">Designed by:<span class="text-dark">Labrin</span></span>
    </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
          
        }
    },
    computed:{
        getYear(){
            return new Date().getFullYear();
        }
    }
};
</script>

<style scoped>

.footer {
  border: 2px solid #007bff;
  border-left: none;
  border-right: none;
  height: 40vh;
}

h5{
    font-size: 15px;
}
</style>
