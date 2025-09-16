<template>
  <div>
    <Navbar />
    <Hero @open-form="showForm = true" />
    <Features />
    <Specialties />
    <Footer />

    <RequestForm v-if="showForm" @close="showForm = false" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import Navbar from "./components/Navbar.vue";
import Hero from "./components/Hero.vue";
import Features from "./components/Features.vue";
import Specialties from "./components/Specialties.vue";
import Footer from "./components/Footer.vue";
import RequestForm from "./components/Requestform.vue";

const showForm = ref(false);
</script>
