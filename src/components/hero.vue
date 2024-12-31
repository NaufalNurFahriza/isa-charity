<template>
    <section class="hero">
      <div class="container">
        <h1 class="hero__title fade-up">About Us</h1>
        <p class="hero__subtitle fade-up">Making a difference in our community</p>
      </div>
    </section>
  </template>
  
  <script>
  import { gsap } from 'gsap'
  
  export default {
    name: 'HeroSection',
    mounted() {
      this.initAnimations()
    },
    methods: {
      initAnimations() {
        gsap.to('.hero__title', {
          opacity: 1,
          y: 0,
          duration: 1,
          ease: 'power3.out'
        })
        
        gsap.to('.hero__subtitle', {
          opacity: 1,
          y: 0,
          duration: 1,
          delay: 0.2,
          ease: 'power3.out'
        })
      }
    }
  }
  </script>
  
  <style lang="scss" scoped>
  .hero {
    background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
                url('@/assets/images/hero-bg.jpg') center/cover;
    height: 400px;
    display: flex;
    align-items: center;
    text-align: center;
    color: #fff;
    
    &__title {
      font-size: 48px;
      margin-bottom: 20px;
      
      @include responsive(mobile) {
        font-size: 36px;
      }
    }
    
    &__subtitle {
      font-size: 24px;
      opacity: 0.9;
      
      @include responsive(mobile) {
        font-size: 18px;
      }
    }
  }
  </style>