<template>
 
      <div class="carousel-item">
        <img src="../assets/image/image1.jpg" alt="" />
      </div>
    
</template>

<script>
export default {

}
</script>

<style scoped >

    /* .carousel{
        height: 35vh;
        background: #000;
        position: relative;
    } */
    .carousel-item{
        display: block;
        position: relative;
        margin-left: 25%;
        margin-right: 25%;
        margin-top: -50px;
        width: 50%;
        overflow: visible;
    }

    .carousel-item img{
        width: 100%;
    }

    .right{
        position: absolute;
        top: 50%;
        right: -30%;
    }

    .left{
        position: absolute;
        top: 50%;
        left: -30%;
    }

    

    @media screen and (max-width: 768px) {
        /* .carousel{
        height: 20vh;
        background: #000;
        position: relative;
    } */
        .carousel-item{
        display: block;
        position: relative;
        margin-left: 20%;
        margin-top: -20px;
        width: 60%;
    }
    .right{
        position: absolute;
        right: -20%;
        
    }
    .left{
        position: absolute;
        left: -20%;
    }
    }
   
</style>