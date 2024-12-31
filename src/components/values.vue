<template>
    <section class="values section">
      <div class="container">
        <h2 class="values__title fade-up">Our Values</h2>
        <div class="values__grid">
          <div v-for="(value, index) in values" 
               :key="index" 
               class="values__item fade-up">
            <h3>{{ value.title }}</h3>
            <p>{{ value.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  import { gsap } from 'gsap'
  import { ScrollTrigger } from 'gsap/ScrollTrigger'
  
  gsap.registerPlugin(ScrollTrigger)
  
  export default {
    name: 'ValuesSection',
    data() {
      return {
        values: [
          {
            title: 'Integrity',
            description: 'We maintain the highest standards of integrity in all our actions.'
          },
          {
            title: 'Compassion',
            description: 'We act with empathy and understanding in everything we do.'
          },
          {
            title: 'Innovation',
            description: 'We seek creative solutions to make a lasting impact.'
          }
        ]
      }
    },
    mounted() {
      this.initAnimations()
    },
    methods: {
      initAnimations() {
        gsap.utils.toArray('.values__item').forEach((element, index) => {
          gsap.from(element, {
            scrollTrigger: {
              trigger: element,
              start: 'top 80%',
              toggleActions: 'play none none reverse'
            },
            opacity: 0,
            y: 30,
            duration: 1,
            delay: index * 0.2,
            ease: 'power3.out'
          })
        })
      }
    }
  }
  </script>
  
  <style lang="scss" scoped>
  .values {
    background: #f8f8f8;
    
    &__title {
      text-align: center;
      font-size: 36px;
      margin-bottom: 50px;
      color: $primary-color;
    }
    
    &__grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 30px;
      
      @include responsive(tablet) {
        grid-template-columns: repeat(2, 1fr);
      }
      
      @include responsive(mobile) {
        grid-template-columns: 1fr;
      }
    }
    
    &__item {
      background: $white;
      padding: 30px;
      border-radius: 10px;
      text-align: center;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
      transition: transform 0.3s ease;
      
      &:hover {
        transform: translateY(-5px);
      }
      
      h3 {
        font-size: 24px;
        margin-bottom: 20px;
        color: $accent-color;
      }
      
      p {
        font-size: 16px;
        line-height: 1.6;
        color: $secondary-color;
      }
    }
  }
  </style>