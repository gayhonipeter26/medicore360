<template>
  <footer class="footer">
    <div class="footer-container">
      <div class="footer-content">
        <div class="footer-brand">
          <div class="brand-logo">
            <div class="logo-icon">
              <div class="medical-cross">
                <div class="cross-horizontal"></div>
                <div class="cross-vertical"></div>
              </div>
            </div>
            <span class="brand-name">MediCore360</span>
          </div>
          <p class="brand-tagline">Empowering Healthcare Excellence</p>
        </div>
        
        <div class="footer-links">
          <div class="link-group">
            <h4>Product</h4>
            <a href="#features">Features</a>
            <a href="#specialties">Specialties</a>
            <a href="#pricing">Pricing</a>
            <a href="#demo">Request Demo</a>
          </div>
          
          <div class="link-group">
            <h4>Support</h4>
            <a href="#help">Help Center</a>
            <a href="#contact">Contact Us</a>
            <a href="#training">Training</a>
            <a href="#documentation">Documentation</a>
          </div>
          
          <div class="link-group">
            <h4>Company</h4>
            <a href="#about">About Us</a>
            <a href="#careers">Careers</a>
            <a href="#news">News</a>
            <a href="#partners">Partners</a>
          </div>
          
          <div class="link-group">
            <h4>Legal</h4>
            <a href="#privacy">Privacy Policy</a>
            <a href="#terms">Terms of Service</a>
            <a href="#compliance">HIPAA Compliance</a>
            <a href="#security">Security</a>
          </div>
        </div>
      </div>
      
      <div class="footer-social">
        <div class="social-links">
          <a href="#" class="social-link" aria-label="LinkedIn">
            <span class="social-icon">💼</span>
          </a>
          <a href="#" class="social-link" aria-label="Twitter">
            <span class="social-icon">🐦</span>
          </a>
          <a href="#" class="social-link" aria-label="Facebook">
            <span class="social-icon">📘</span>
          </a>
          <a href="#" class="social-link" aria-label="YouTube">
            <span class="social-icon">📺</span>
          </a>
        </div>
        <div class="contact-info">
          <div class="contact-item">
            <span class="contact-icon">📧</span>
            <span>support@medicore360.com</span>
          </div>
          <div class="contact-item">
            <span class="contact-icon">📞</span>
            <span>1-800-MEDCORE</span>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <div class="footer-divider"></div>
        <div class="footer-bottom-content">
          <div class="copyright">
            © 2025 MediCore360. All Rights Reserved.
          </div>
          <div class="footer-badges">
            <div class="compliance-badge">
              <span class="badge-icon">🔒</span>
              <span>HIPAA Compliant</span>
            </div>
            <div class="compliance-badge">
              <span class="badge-icon">✓</span>
              <span>SOC 2 Certified</span>
            </div>
            <div class="compliance-badge">
              <span class="badge-icon">🛡️</span>
              <span>ISO 27001</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: linear-gradient(135deg, #1e40af 0%, #3b82f6 100%);
  color: white;
  position: relative;
  overflow: hidden;
}

.footer::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(circle at 20% 80%, rgba(147, 197, 253, 0.1) 0%, transparent 50%),
              radial-gradient(circle at 80% 20%, rgba(219, 234, 254, 0.08) 0%, transparent 50%);
  pointer-events: none;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 3rem 2rem 1rem;
  position: relative;
  z-index: 1;
}

.footer-content {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 3rem;
  margin-bottom: 2rem;
}

.footer-brand {
  max-width: 300px;
}

.brand-logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 1rem;
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

.brand-name {
  font-size: 1.5rem;
  font-weight: 700;
  color: white;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.brand-tagline {
  color: rgba(255, 255, 255, 0.8);
  font-size: 0.95rem;
  line-height: 1.5;
  margin: 0 0 1.5rem 0;
}

.footer-links {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 2rem;
}

.link-group h4 {
  color: white;
  font-size: 1rem;
  font-weight: 600;
  margin: 0 0 1rem 0;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
}

.link-group a {
  display: block;
  color: rgba(255, 255, 255, 0.8);
  text-decoration: none;
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
  transition: all 0.3s ease;
  padding: 0.25rem 0;
}

.link-group a:hover {
  color: white;
  transform: translateX(4px);
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.2);
}

.footer-social {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
  padding: 1.5rem 0;
  border-top: 1px solid rgba(255, 255, 255, 0.15);
  border-bottom: 1px solid rgba(255, 255, 255, 0.15);
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-link {
  width: 44px;
  height: 44px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  transition: all 0.3s ease;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.social-link:hover {
  background: rgba(255, 255, 255, 0.2);
  transform: translateY(-2px);
}

.social-icon {
  font-size: 1.2rem;
  filter: grayscale(0%);
}

.contact-info {
  display: flex;
  gap: 2rem;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: rgba(255, 255, 255, 0.9);
  font-size: 0.9rem;
}

.contact-icon {
  font-size: 1rem;
}

.footer-bottom {
  position: relative;
}

.footer-divider {
  height: 1px;
  background: linear-gradient(90deg, transparent 0%, rgba(255, 255, 255, 0.3) 50%, transparent 100%);
  margin-bottom: 1.5rem;
}

.footer-bottom-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.copyright {
  color: rgba(255, 255, 255, 0.8);
  font-size: 0.9rem;
}

.footer-badges {
  display: flex;
  gap: 1.5rem;
}

.compliance-badge {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  background: rgba(255, 255, 255, 0.1);
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.8rem;
  color: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.15);
}

.badge-icon {
  font-size: 0.9rem;
}

/* Mobile Responsive */
@media (max-width: 768px) {
  .footer-container {
    padding: 2rem 1rem 1rem;
  }
  
  .footer-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .footer-links {
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }
  
  .footer-social {
    flex-direction: column;
    gap: 1.5rem;
    text-align: center;
  }
  
  .contact-info {
    flex-direction: column;
    gap: 1rem;
  }
  
  .footer-bottom-content {
    flex-direction: column;
    gap: 1rem;
    text-align: center;
  }
  
  .footer-badges {
    flex-wrap: wrap;
    justify-content: center;
    gap: 1rem;
  }
}

@media (max-width: 480px) {
  .footer-container {
    padding: 1.5rem 1rem 1rem;
  }
  
  .footer-links {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  
  .social-links {
    flex-wrap: wrap;
    justify-content: center;
  }
  
  .footer-badges {
    flex-direction: column;
    align-items: center;
  }
  
  .compliance-badge {
    padding: 0.4rem 0.8rem;
    font-size: 0.75rem;
  }
}</style>