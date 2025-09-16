<template>
  <header class="navbar">
    <div class="navbar-container">
      <div class="brand">
        <div class="logo-icon">
          <div class="medical-cross">
            <div class="cross-horizontal"></div>
            <div class="cross-vertical"></div>
          </div>
        </div>
        <h1>MediCore360</h1>
      </div>
      <nav class="nav-menu">
        <a href="#features" class="nav-link">Features</a>
        <a href="#specialties" class="nav-link">Specialties</a>
        <a href="#contact" class="nav-link">Contact</a>
      </nav>
      <div class="mobile-menu-toggle" @click="toggleMobileMenu">
        <span class="hamburger-line"></span>
        <span class="hamburger-line"></span>
        <span class="hamburger-line"></span>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      mobileMenuOpen: false
    }
  },
  methods: {
    toggleMobileMenu() {
      this.mobileMenuOpen = !this.mobileMenuOpen;
      const navbar = document.querySelector('.navbar');
      navbar.classList.toggle('mobile-menu-active');
    }
  }
}
</script>

<style scoped>
.navbar {
  background: linear-gradient(135deg, #1e40af 0%, #3b82f6 100%);
  padding: 0;
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: 0 2px 20px rgba(30, 64, 175, 0.15);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.navbar-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
}

.brand {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  cursor: pointer;
  transition: transform 0.2s ease;
}

.brand:hover {
  transform: scale(1.02);
}

.logo-icon {
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.15);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.medical-cross {
  position: relative;
  width: 20px;
  height: 20px;
}

.cross-horizontal,
.cross-vertical {
  position: absolute;
  background: white;
  border-radius: 2px;
}

.cross-horizontal {
  width: 16px;
  height: 4px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.cross-vertical {
  width: 4px;
  height: 16px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.brand h1 {
  color: white;
  margin: 0;
  font-size: 1.5rem;
  font-weight: 700;
  letter-spacing: -0.02em;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.nav-menu {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.nav-link {
  color: rgba(255, 255, 255, 0.9);
  text-decoration: none;
  font-weight: 500;
  font-size: 0.95rem;
  padding: 0.5rem 1rem;
  border-radius: 8px;
  transition: all 0.3s ease;
  position: relative;
  letter-spacing: 0.01em;
}

.nav-link::before {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 0;
  height: 2px;
  background: white;
  border-radius: 1px;
  transition: all 0.3s ease;
  transform: translateX(-50%);
}

.nav-link:hover {
  color: white;
  background: rgba(255, 255, 255, 0.1);
  transform: translateY(-1px);
}

.nav-link:hover::before {
  width: 80%;
}

.nav-link:active {
  transform: translateY(0);
}

.mobile-menu-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
  padding: 0.5rem;
  border-radius: 6px;
  transition: background 0.3s ease;
}

.mobile-menu-toggle:hover {
  background: rgba(255, 255, 255, 0.1);
}

.hamburger-line {
  width: 24px;
  height: 3px;
  background: white;
  border-radius: 2px;
  margin: 2px 0;
  transition: all 0.3s ease;
}

/* Mobile Styles */
@media (max-width: 768px) {
  .navbar-container {
    padding: 1rem;
  }
  
  .brand h1 {
    font-size: 1.25rem;
  }
  
  .logo-icon {
    width: 36px;
    height: 36px;
  }
  
  .medical-cross {
    width: 18px;
    height: 18px;
  }
  
  .cross-horizontal {
    width: 14px;
    height: 3px;
  }
  
  .cross-vertical {
    width: 3px;
    height: 14px;
  }
  
  .nav-menu {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background: linear-gradient(135deg, #1e40af 0%, #3b82f6 100%);
    flex-direction: column;
    gap: 0;
    padding: 1rem;
    box-shadow: 0 4px 20px rgba(30, 64, 175, 0.3);
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    transform: translateY(-100%);
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
  }
  
  .mobile-menu-active .nav-menu {
    transform: translateY(0);
    opacity: 1;
    visibility: visible;
  }
  
  .nav-link {
    width: 100%;
    text-align: center;
    padding: 1rem;
    border-radius: 8px;
    margin: 0.25rem 0;
  }
  
  .nav-link::before {
    display: none;
  }
  
  .mobile-menu-toggle {
    display: flex;
  }
  
  .mobile-menu-active .hamburger-line:nth-child(1) {
    transform: rotate(45deg) translate(6px, 6px);
  }
  
  .mobile-menu-active .hamburger-line:nth-child(2) {
    opacity: 0;
  }
  
  .mobile-menu-active .hamburger-line:nth-child(3) {
    transform: rotate(-45deg) translate(6px, -6px);
  }
}

@media (max-width: 480px) {
  .navbar-container {
    padding: 0.75rem;
  }
  
  .brand h1 {
    font-size: 1.125rem;
  }
  
  .logo-icon {
    width: 32px;
    height: 32px;
  }
}

/* Smooth scrolling for anchor links */
html {
  scroll-behavior: smooth;
}

/* Active link state */
.nav-link.active {
  background: rgba(255, 255, 255, 0.15);
  color: white;
}

.nav-link.active::before {
  width: 80%;
}</style>