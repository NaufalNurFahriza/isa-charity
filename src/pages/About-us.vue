<!-- src/pages/About-us.vue -->
<template>
    <div class="about-page">
      <section-1 />
      <section-2 />
      <section-3 />
    </div>
  </template>
  
  <script>
  import Section1 from '@/components/section-1.vue'
  import Section2 from '@/components/section-2.vue'
  import Section3 from '@/components/section-3.vue'
  
  export default {
    name: 'AboutUs',
    components: {
      Section1,
      Section2,
      Section3
    }
  }
  </script>
  
  <style lang="scss" scoped>
  .about-page {
    padding-top: 80px; // Account for fixed header
  }
  </style>