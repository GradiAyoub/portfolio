<script setup>

defineProps({
    data: Object
})

</script>

<template>
 <!-- about -->
 <section id="about" data-aos="fade-up">
    <h1 class="text-center sectionTitle">ABOUT ME</h1>
    <div class="container row">
      <div class="col-lg-6 px-5 d-flex justify-content-lg-end justify-content-center">
        <img :src="data.img" height="400px" class="shadow rounded border border-dark" data-aos="fade-up-right">
      </div>
      <div class="col-lg-6 mt-3 d-flex align-items-center" data-aos="fade-up-left">
        <div>
          <p class="fs-4 px-4">{{data.text}} </p>
            <div class="text-center px-4 text-lg-start">
              <a  href="./gradi_ayoub_CV.pdf" class="btn btn-light m-2 text-center" download>Download CV</a>
            </div>
        </div>
      </div>
    </div>
  </section>
</template>