<template>
  <div id="app">
    <Navbar />
    <HeroSection />
    <AdvantagesSection />
  </div>
</template>

<script>

import Navbar from '../src/components/Navbar/Navbar.vue';
import HeroSection from '../src/components/HeroSection/HeroSection.vue';
import AdvantagesSection from '../src/components/AdvantagesSection/AdvantagesSection.vue';


export default {
  components: {
    Navbar,
    HeroSection,
    AdvantagesSection
  }
};
</script>

<style>
body {
  margin: 0;
  font-family: 'TT Travels', sans-serif;
  background-color: #fff;
}
</style>
