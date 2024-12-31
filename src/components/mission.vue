<template>
    <section class="mission section">
      <div class="container">
        <div class="mission__content">
          <h2 class="mission__title fade-up">Our Mission</h2>
          <p class="mission__text fade-up">
            We strive to create positive change through charitable initiatives and community engagement.
            Our focus is on sustainable development and empowering individuals to reach their full potential.
          </p>
        </div>
        <div class="mission__image fade-up">
          <img src="@/assets/images/mission.jpg" alt="Our Mission" />
        </div>
      </div>
    </section>
  </template>
  
  <script>
  import { gsap } from 'gsap'
  import { ScrollTrigger } from 'gsap/ScrollTrigger'
  
  gsap.registerPlugin(ScrollTrigger)
  
  export default {
    name: 'MissionSection',
    mounted() {
      this.initAnimations()
    },
    methods: {
      initAnimations() {
        gsap.utils.toArray('.fade-up').forEach(element => {
          gsap.from(element, {
            scrollTrigger: {
              trigger: element,
              start: 'top 80%',
              toggleActions: 'play none none reverse'
            },
            opacity: 0,
            y: 30,
            duration: 1,
            ease: 'power3.out'
          })
        })
      }
    }
  }
  </script>
  
  <style lang="scss" scoped>
  .mission {
    &__content {
      max-width: 600px;
      margin: 0 auto;
      text-align: center;
    }
    
    &__title {
      font-size: 36px;
      margin-bottom: 30px;
      color: $primary-color;
    }
    
    &__text {
      font-size: 18px;
      line-height: 1.8;
      margin-bottom: 40px;
      color: $secondary-color;
    }
    
    &__image {
      max-width: 800px;
      margin: 0 auto;
      
      img {
        width: 100%;
        border-radius: 10px;
        box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
      }
    }
  }
  </style>