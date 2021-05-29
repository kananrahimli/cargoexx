<template>
  <div class="contact px-5"  id="contact">
    <div class="row">
      <div class="col-md-5 mb-5">
        <img src="../assets/Contact.svg" alt="" class="img-fluid" />
      </div>
      <div class="col-md-6  ml-md-5 " >
        <h1 class="text-primary px-2">Ready to discuss?</h1>
        <p class="px-2">FIll out the form or email us</p>
        <div class="input-texts row mt-3">
          <div class="col-md-6 px-2">
            <input
              type="text"
              placeholder="Name"
              class="form-control my-1 p-2"
            />
          </div>
          <div class="col-md-6 px-2">
            <input
              type="text"
              placeholder="Surname"
              class="form-control my-1 p-2"
            />
          </div>
          <div class="col-md-12 px-2">
            <input
              type="text"
              placeholder="Your message"
              class="form-control my-1 p-2"
            />
          </div>
          <button type="submit" class="mt-3 ">
            <p class="send-text font-weight-bold text-light">Send</p>
            <img src="../assets/sendButton.svg" width="80px" alt="" />
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>


.contact {
  background: lightblue;
  padding-top: 90px;
  padding-bottom: 70px;
}
/* .contact  img {
  width: 100%;
} */

.contact input {
  border: 1px solid rgb(95, 95, 255);
  background: none;
  border-radius: 20px;
}
button {
  position: relative;
  margin-left: 80%;
}

button .send-text {
  position: absolute;
  left: 20%;
  top: 20%;
  font-weight: 900;
}


/* responsive */

@media screen and (max-width: 768px) {
  button{
 margin-left: 50%;
 transform: translate(-50%);
}
}
</style>
