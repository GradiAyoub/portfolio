<script setup>
import Project from './Project.vue';

defineProps({
    data: Object
})

</script>

<template>

<section id="projects"  class="container">
    <h1 class="text-center sectionTitle" data-aos="fade-up">projects</h1>
    <div class="container row">

        <div class="col-lg-4 col-md-6 my-4" v-for="project in data" :key="data.id">
           <Project :data="project" />
        </div>
        
    </div>
</section>





</template>