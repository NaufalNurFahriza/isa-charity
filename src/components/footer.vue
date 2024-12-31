<template>
    <footer class="footer">
      <div class="container">
        <div class="footer__grid">
          <div class="footer__info">
            <img src="@/assets/images/logo.svg" alt="ISA Charity" class="footer__logo" />
            <p>Making a positive impact in our community through charitable initiatives and sustainable development.</p>
          </div>
          
          <div class="footer__links">
            <h4>Quick Links</h4>
            <ul>
              <li><router-link to="/">Home</router-link></li>
              <li><router-link to="/about-us">About Us</router-link></li>
              <li><router-link to="/contact">Contact</router-link></li>
            </ul>
          </div>
          
          <div class="footer__contact">
            <h4>Contact Us</h4>
            <p>Email: info@isacharity.org</p>
            <p>Phone: (123) 456-7890</p>
            <p>Address: 123 Charity Street, City, Country</p>
          </div>
        </div>
        
        <div class="footer__bottom">
          <p>&copy; 2024 ISA Charity. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    name: 'Footer'
  }
  </script>
  
  <style lang="scss" scoped>
  .footer {
    background: $primary-color;
    color: $white;
    padding: 60px 0 20px;
    
    &__grid {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr;
      gap: 40px;
      margin-bottom: 40px;
      
      @include responsive(tablet) {
        grid-template-columns: 1fr 1fr;
      }
      
      @include responsive(mobile) {
        grid-template-columns: 1fr;
      }
    }
    
    &__info {
      p {
        margin-top: 20px;
        opacity: 0.8;
      }
    }
    
    &__logo {
      height: 40px;
    }
    
    &__links {
      h4 {
        margin-bottom: 20px;
      }
      
      ul {
        list-style: none;
        
        li {
          margin-bottom: 10px;
          
          a {
            color: $white;
            text-decoration: none;
            opacity: 0.8;
            transition: opacity 0.3s ease;
            
            &:hover {
              opacity: 1;
            }
          }
        }
      }
    }
    
    &__contact {
      h4 {
        margin-bottom: 20px;
      }
      
      p {
        margin-bottom: 10px;
        opacity: 0.8;
      }
    }
    
    &__bottom {
      border-top: 1px solid rgba($white, 0.1);
      padding-top: 20px;
      text-align: center;
      
      p {
        opacity: 0.6;
        font-size: 14px;
      }
    }
  }
  </style>