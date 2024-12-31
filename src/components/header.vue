<template>
    <header class="header" :class="{ 'header--scrolled': isScrolled }">
      <div class="container header__container">
        <router-link to="/" class="header__logo">
          <img src="@/assets/images/logo.svg" alt="ISA Charity" />
        </router-link>
        
        <nav class="header__nav" :class="{ 'header__nav--active': isMenuOpen }">
          <ul class="header__nav-list">
            <li><router-link to="/" class="header__nav-link">Home</router-link></li>
            <li><router-link to="/about-us" class="header__nav-link">About Us</router-link></li>
            <li><router-link to="/contact" class="header__nav-link">Contact</router-link></li>
          </ul>
        </nav>
        
        <button class="header__menu-btn" @click="toggleMenu">
          <span></span>
          <span></span>
          <span></span>
        </button>
      </div>
    </header>
  </template>
  
  <script>
  import { gsap } from 'gsap'
  
  export default {
    name: 'Header',
    data() {
      return {
        isScrolled: false,
        isMenuOpen: false
      }
    },
    mounted() {
      window.addEventListener('scroll', this.handleScroll)
      this.initAnimation()
    },
    beforeUnmount() {
      window.removeEventListener('scroll', this.handleScroll)
    },
    methods: {
      handleScroll() {
        this.isScrolled = window.scrollY > 50
      },
      toggleMenu() {
        this.isMenuOpen = !this.isMenuOpen
      },
      initAnimation() {
        gsap.from('.header', {
          duration: 1,
          y: -100,
          opacity: 0,
          ease: 'power3.out'
        })
      }
    }
  }
  </script>
  
  <style lang="scss" scoped>
  .header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
    background: transparent;
    transition: all 0.3s ease;
    
    &--scrolled {
      background: $white;
      box-shadow: 0 2px 10px rgba($black, 0.1);
    }
    
    &__container {
      @include flex-center;
      justify-content: space-between;
      height: 80px;
    }
    
    &__logo {
      img {
        height: 40px;
      }
    }
    
    &__nav {
      @include responsive(tablet) {
        position: fixed;
        top: 80px;
        left: 0;
        width: 100%;
        background: $white;
        transform: translateX(-100%);
        transition: transform 0.3s ease;
        
        &--active {
          transform: translateX(0);
        }
      }
    }
    
    &__nav-list {
      display: flex;
      list-style: none;
      gap: 40px;
      
      @include responsive(tablet) {
        flex-direction: column;
        padding: 20px;
        gap: 20px;
      }
    }
    
    &__nav-link {
      color: $primary-color;
      text-decoration: none;
      font-weight: 500;
      transition: color 0.3s ease;
      
      &:hover {
        color: $accent-color;
      }
    }
    
    &__menu-btn {
      display: none;
      
      @include responsive(tablet) {
        display: block;
        background: none;
        border: none;
        cursor: pointer;
        padding: 10px;
        
        span {
          display: block;
          width: 25px;
          height: 2px;
          background: $primary-color;
          margin: 5px 0;
          transition: all 0.3s ease;
        }
      }
    }
  }
  </style>