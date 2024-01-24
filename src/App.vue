<script setup>
import data from './data.json'
import Header from './components/Header.vue';
import About from './components/About.vue';
import Skills from './components/Skills.vue';
import Projects from './components/Projects.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';


</script>

<template>
  <div>
    <Header />
    <About :data="data.about"  />
    <Skills />
    <Projects :data="data.projects" />
    <Contact/>
    <Footer />
  </div>

</template>
