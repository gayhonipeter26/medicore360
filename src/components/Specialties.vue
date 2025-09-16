<template>
  <section id="specialties" class="specialties">
    <div class="specialties-container">
      <div class="section-header">
        <h2>Supported Facilities</h2>
        <p class="section-subtitle">Comprehensive healthcare management solutions tailored for every type of medical facility</p>
      </div>
      
      <div class="facilities-grid">
        <div class="facility-card" v-for="(facility, index) in facilities" :key="index">
          <div class="facility-icon-container">
            <div class="facility-icon" :class="`icon-${index + 1}`">
              <span class="icon">{{ facility.icon }}</span>
            </div>
            <div class="icon-glow"></div>
          </div>
          <div class="facility-content">
            <h3>{{ facility.title }}</h3>
            <p>{{ facility.description }}</p>
            <ul class="feature-list">
              <li v-for="feature in facility.features" :key="feature">
                <span class="check-icon">✓</span>
                {{ feature }}
              </li>
            </ul>
          </div>
          <div class="facility-stats">
            <div class="stat">
              <span class="stat-number">{{ facility.users }}</span>
              <span class="stat-label">Active Users</span>
            </div>
            <div class="stat">
              <span class="stat-number">{{ facility.facilities }}</span>
              <span class="stat-label">Facilities</span>
            </div>
          </div>
        </div>
      </div>
      
      <div class="cta-section">
        <div class="cta-content">
          <h3>Ready to modernize your facility?</h3>
          <p>Join thousands of healthcare professionals who trust MediCore360</p>
          <button class="cta-button">
            <span>Get Started Today</span>
            <span class="arrow">→</span>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      facilities: [
        {
          title: "Hospitals",
          icon: "🏥",
          description: "Complete hospital management system with advanced patient care coordination and multi-department integration.",
          features: ["Patient Management", "Staff Scheduling", "Emergency Care", "Multi-Department"],
          users: "50K+",
          facilities: "1,200+"
        },
        {
          title: "Dental Clinics",
          icon: "🦷",
          description: "Specialized dental practice management with appointment scheduling, treatment planning, and billing.",
          features: ["Treatment Plans", "Digital Records", "Appointment Booking", "Insurance Claims"],
          users: "25K+",
          facilities: "800+"
        },
        {
          title: "Pharmacies",
          icon: "💊",
          description: "Comprehensive pharmacy management with inventory control, prescription tracking, and compliance monitoring.",
          features: ["Inventory Control", "Prescription Management", "Drug Interactions", "Compliance Tracking"],
          users: "15K+",
          facilities: "600+"
        },
        {
          title: "Laboratories",
          icon: "🔬",
          description: "Advanced laboratory information system with test management, result reporting, and quality control.",
          features: ["Test Management", "Result Reporting", "Quality Control", "Equipment Integration"],
          users: "12K+",
          facilities: "400+"
        }
      ]
    }
  }
}
</script>

<style scoped>
.specialties {
  background: white;
  padding: 5rem 2rem;
  position: relative;
  overflow: hidden;
}

.specialties::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(circle at 70% 30%, rgba(59, 130, 246, 0.03) 0%, transparent 50%),
              radial-gradient(circle at 30% 70%, rgba(147, 197, 253, 0.05) 0%, transparent 50%);
  pointer-events: none;
}

.specialties-container {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  z-index: 1;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-header h2 {
  font-size: 2.75rem;
  font-weight: 700;
  color: #1e293b;
  margin-bottom: 1rem;
  letter-spacing: -0.02em;
  position: relative;
}

.section-header h2::after {
  content: '';
  position: absolute;
  bottom: -8px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 4px;
  background: linear-gradient(135deg, #3b82f6 0%, #1d4ed8 100%);
  border-radius: 2px;
}

.section-subtitle {
  font-size: 1.125rem;
  color: #64748b;
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.6;
}

.facilities-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.facility-card {
  background: white;
  border-radius: 24px;
  padding: 2.5rem 2rem;
  position: relative;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  border: 1px solid rgba(226, 232, 240, 0.8);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  overflow: hidden;
  cursor: pointer;
}

.facility-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(135deg, #3b82f6 0%, #1d4ed8 100%);
  transform: scaleX(0);
  transition: transform 0.4s ease;
}

.facility-card:hover::before {
  transform: scaleX(1);
}

.facility-card:hover {
  transform: translateY(-12px);
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
  border-color: rgba(59, 130, 246, 0.2);
}

.facility-icon-container {
  position: relative;
  display: flex;
  justify-content: center;
  margin-bottom: 2rem;
}

.facility-icon {
  width: 100px;
  height: 100px;
  border-radius: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  transition: all 0.3s ease;
  z-index: 2;
}

.icon-1 {
  background: linear-gradient(135deg, #dbeafe 0%, #bfdbfe 100%);
}

.icon-2 {
  background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%);
}

.icon-3 {
  background: linear-gradient(135deg, #d1fae5 0%, #a7f3d0 100%);
}

.icon-4 {
  background: linear-gradient(135deg, #fce7f3 0%, #fbcfe8 100%);
}

.facility-card:hover .facility-icon {
  transform: scale(1.1) rotate(5deg);
}

.icon {
  font-size: 3rem;
  filter: grayscale(20%);
  transition: filter 0.3s ease;
}

.facility-card:hover .icon {
  filter: grayscale(0%);
}

.icon-glow {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 120px;
  height: 120px;
  background: radial-gradient(circle, rgba(59, 130, 246, 0.1) 0%, transparent 70%);
  border-radius: 50%;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.facility-card:hover .icon-glow {
  opacity: 1;
}

.facility-content {
  text-align: center;
  margin-bottom: 2rem;
}

.facility-content h3 {
  font-size: 1.5rem;
  font-weight: 600;
  color: #1e293b;
  margin-bottom: 1rem;
  line-height: 1.3;
}

.facility-content p {
  color: #64748b;
  line-height: 1.6;
  font-size: 0.95rem;
  margin-bottom: 1.5rem;
}

.feature-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.feature-list li {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 0.5rem;
  font-size: 0.9rem;
  color: #475569;
}

.check-icon {
  color: #10b981;
  font-weight: bold;
  font-size: 0.8rem;
}

.facility-stats {
  display: flex;
  justify-content: space-around;
  padding-top: 1.5rem;
  border-top: 1px solid #f1f5f9;
}

.stat {
  text-align: center;
}

.stat-number {
  display: block;
  font-size: 1.5rem;
  font-weight: 700;
  color: #3b82f6;
  margin-bottom: 0.25rem;
}

.stat-label {
  font-size: 0.8rem;
  color: #64748b;
  font-weight: 500;
}

.cta-section {
  background: linear-gradient(135deg, #1e40af 0%, #3b82f6 100%);
  border-radius: 24px;
  padding: 3rem 2rem;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.cta-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(circle at 30% 20%, rgba(255, 255, 255, 0.1) 0%, transparent 50%),
              radial-gradient(circle at 70% 80%, rgba(255, 255, 255, 0.05) 0%, transparent 50%);
  pointer-events: none;
}

.cta-content {
  position: relative;
  z-index: 1;
}

.cta-content h3 {
  font-size: 2rem;
  font-weight: 700;
  color: white;
  margin-bottom: 1rem;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.cta-content p {
  font-size: 1.125rem;
  color: rgba(255, 255, 255, 0.9);
  margin-bottom: 2rem;
  max-width: 500px;
  margin-left: auto;
  margin-right: auto;
}

.cta-button {
  background: white;
  color: #1e40af;
  border: none;
  padding: 1rem 2.5rem;
  border-radius: 16px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

.cta-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
}

.arrow {
  transition: transform 0.3s ease;
}

.cta-button:hover .arrow {
  transform: translateX(4px);
}

/* Animation for cards appearing on scroll */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.facility-card {
  animation: fadeInUp 0.6s ease-out;
}

.facility-card:nth-child(1) { animation-delay: 0.1s; }
.facility-card:nth-child(2) { animation-delay: 0.2s; }
.facility-card:nth-child(3) { animation-delay: 0.3s; }
.facility-card:nth-child(4) { animation-delay: 0.4s; }

/* Mobile Responsive */
@media (max-width: 768px) {
  .specialties {
    padding: 3rem 1rem;
  }
  
  .section-header h2 {
    font-size: 2.25rem;
  }
  
  .section-subtitle {
    font-size: 1rem;
  }
  
  .facilities-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .facility-card {
    padding: 2rem 1.5rem;
  }
  
  .facility-icon {
    width: 80px;
    height: 80px;
  }
  
  .icon {
    font-size: 2.5rem;
  }
  
  .cta-section {
    padding: 2rem 1.5rem;
  }
  
  .cta-content h3 {
    font-size: 1.75rem;
  }
  
  .cta-content p {
    font-size: 1rem;
  }
}

@media (max-width: 480px) {
  .specialties {
    padding: 2rem 1rem;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
  
  .facility-card {
    padding: 1.5rem 1rem;
  }
  
  .facility-icon {
    width: 70px;
    height: 70px;
  }
  
  .icon {
    font-size: 2rem;
  }
  
  .facility-stats {
    flex-direction: column;
    gap: 1rem;
  }
  
  .cta-content h3 {
    font-size: 1.5rem;
  }
  
  .cta-button {
    padding: 0.875rem 2rem;
    font-size: 0.9rem;
  }
}
</style>