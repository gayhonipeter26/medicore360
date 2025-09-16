<template>
  <section class="hero">
    <div class="hero-container">
      <div class="hero-content">
        <h2>Modern Hospital Management System</h2>
        <p>
          Tailored for hospitals, dental clinics, pharmacies, and labs.<br />
          Empowering staff, simplifying workflows, and enhancing patient care.
        </p>
        <button class="btn" @click="$emit('open-form')">Request an Account</button>
      </div>
      <div class="hero-illustration">
        <div class="doctor-card">
          <div class="floating-icons">
            <div class="icon icon-1">📊</div>
            <div class="icon icon-2">✓</div>
            <div class="icon icon-3">🔗</div>
          </div>
          <div class="doctor-avatar">
            <div class="doctor-face">
              <div class="hair"></div>
              <div class="face">
                <div class="eyes">
                  <div class="eye left"></div>
                  <div class="eye right"></div>
                </div>
                <div class="mouth"></div>
              </div>
            </div>
            <div class="stethoscope"></div>
            <div class="coat"></div>
            <div class="tablet"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
  padding: 4rem 2rem;
  min-height: 600px;
  display: flex;
  align-items: center;
}

.hero-container {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.hero-content {
  text-align: left;
}

.hero h2 {
  font-size: 3rem;
  font-weight: 700;
  color: #1e293b;
  margin-bottom: 1.5rem;
  line-height: 1.2;
  letter-spacing: -0.02em;
}

.hero p {
  font-size: 1.125rem;
  color: #64748b;
  margin-bottom: 2rem;
  line-height: 1.6;
  max-width: 500px;
}

.btn {
  background: linear-gradient(135deg, #3b82f6 0%, #1d4ed8 100%);
  color: white;
  border: none;
  padding: 1rem 2rem;
  border-radius: 12px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(59, 130, 246, 0.3);
  text-transform: none;
}

.btn:hover {
  background: linear-gradient(135deg, #1d4ed8 0%, #1e40af 100%);
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(59, 130, 246, 0.4);
}

.btn:active {
  transform: translateY(0);
}

.hero-illustration {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.doctor-card {
  background: rgba(219, 234, 254, 0.8);
  border-radius: 24px;
  padding: 3rem 2rem;
  position: relative;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(147, 197, 253, 0.3);
  min-height: 400px;
  width: 320px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.floating-icons {
  position: absolute;
  inset: 0;
}

.icon {
  position: absolute;
  background: #60a5fa;
  color: white;
  width: 48px;
  height: 48px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  box-shadow: 0 4px 15px rgba(96, 165, 250, 0.3);
  animation: float 3s ease-in-out infinite;
}

.icon-1 {
  top: 20px;
  left: 20px;
  animation-delay: 0s;
}

.icon-2 {
  top: 40px;
  right: 30px;
  animation-delay: 1s;
}

.icon-3 {
  bottom: 60px;
  right: 20px;
  animation-delay: 2s;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-10px);
  }
}

.doctor-avatar {
  position: relative;
  z-index: 2;
}

.doctor-face {
  position: relative;
  margin-bottom: 1rem;
}

.hair {
  width: 80px;
  height: 40px;
  background: #1e293b;
  border-radius: 40px 40px 0 0;
  margin: 0 auto 5px;
}

.face {
  width: 70px;
  height: 80px;
  background: #fbbf24;
  border-radius: 35px;
  position: relative;
  margin: 0 auto;
}

.eyes {
  display: flex;
  justify-content: space-between;
  padding: 20px 15px 0;
}

.eye {
  width: 8px;
  height: 8px;
  background: #1e293b;
  border-radius: 50%;
}

.mouth {
  width: 12px;
  height: 6px;
  background: #dc2626;
  border-radius: 0 0 12px 12px;
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
}

.stethoscope {
  position: absolute;
  top: 60px;
  left: 50%;
  transform: translateX(-50%);
  width: 4px;
  height: 60px;
  background: #374151;
  border-radius: 2px;
}

.stethoscope::before {
  content: '';
  position: absolute;
  bottom: -8px;
  left: 50%;
  transform: translateX(-50%);
  width: 16px;
  height: 16px;
  border: 3px solid #374151;
  border-radius: 50%;
  background: transparent;
}

.coat {
  width: 100px;
  height: 120px;
  background: white;
  border-radius: 8px;
  margin: 0 auto;
  position: relative;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.coat::before {
  content: '';
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 20px;
  background: #3b82f6;
  border-radius: 0 0 8px 8px;
}

.tablet {
  width: 40px;
  height: 60px;
  background: #1f2937;
  border-radius: 6px;
  position: absolute;
  bottom: 20px;
  right: -20px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
}

.tablet::before {
  content: '';
  position: absolute;
  top: 8px;
  left: 4px;
  right: 4px;
  bottom: 8px;
  background: #60a5fa;
  border-radius: 2px;
}

@media (max-width: 768px) {
  .hero-container {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }
  
  .hero-content {
    text-align: center;
  }
  
  .hero h2 {
    font-size: 2.5rem;
  }
  
  .doctor-card {
    width: 280px;
    min-height: 350px;
  }
}

@media (max-width: 480px) {
  .hero {
    padding: 2rem 1rem;
  }
  
  .hero h2 {
    font-size: 2rem;
  }
  
  .doctor-card {
    width: 250px;
    min-height: 300px;
    padding: 2rem 1rem;
  }
}</style>