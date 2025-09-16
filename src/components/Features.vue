<template>
  <section id="features" class="features">
    <div class="features-container">
      <div class="section-header">
        <h2>Key Features</h2>
        <p>Comprehensive solutions designed to streamline your healthcare operations</p>
      </div>
      
      <div class="features-grid">
        <div class="feature-card" v-for="(feature, index) in features" :key="index">
          <div class="feature-icon">
            <div class="icon-wrapper" :class="`icon-${index + 1}`">
              <span class="icon">{{ feature.icon }}</span>
            </div>
          </div>
          <div class="feature-content">
            <h3>{{ feature.title }}</h3>
            <p>{{ feature.description }}</p>
          </div>
          <div class="feature-hover-effect"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      features: [
        {
          title: "Staff & Patient Management",
          description: "Comprehensive management system for staff scheduling, patient records, and administrative tasks with real-time updates.",
          icon: "👥"
        },
        {
          title: "Pharmacy & Billing System",
          description: "Integrated pharmacy inventory management with automated billing, insurance processing, and payment tracking.",
          icon: "💊"
        },
        {
          title: "Lab Test Reports",
          description: "Digital lab management with automated report generation, result tracking, and seamless integration with patient records.",
          icon: "🔬"
        },
        {
          title: "Appointment Scheduling",
          description: "Smart scheduling system with automated reminders, conflict resolution, and multi-location support.",
          icon: "📅"
        }
      ]
    }
  }
}
</script>

<style scoped>
.features {
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
  padding: 5rem 2rem;
  position: relative;
  overflow: hidden;
}

.features::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(circle at 30% 20%, rgba(59, 130, 246, 0.05) 0%, transparent 50%),
              radial-gradient(circle at 70% 80%, rgba(147, 197, 253, 0.08) 0%, transparent 50%);
  pointer-events: none;
}

.features-container {
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

.section-header p {
  font-size: 1.125rem;
  color: #64748b;
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.6;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.feature-card {
  background: white;
  border-radius: 20px;
  padding: 2.5rem 2rem;
  position: relative;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  border: 1px solid rgba(226, 232, 240, 0.8);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  overflow: hidden;
  cursor: pointer;
}

.feature-card::before {
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

.feature-card:hover::before {
  transform: scaleX(1);
}

.feature-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.12);
  border-color: rgba(59, 130, 246, 0.2);
}

.feature-hover-effect {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(circle at var(--mouse-x, 50%) var(--mouse-y, 50%), 
              rgba(59, 130, 246, 0.03) 0%, transparent 50%);
  opacity: 0;
  transition: opacity 0.3s ease;
  pointer-events: none;
}

.feature-card:hover .feature-hover-effect {
  opacity: 1;
}

.feature-icon {
  margin-bottom: 1.5rem;
  display: flex;
  justify-content: center;
}

.icon-wrapper {
  width: 80px;
  height: 80px;
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  transition: all 0.3s ease;
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

.feature-card:hover .icon-wrapper {
  transform: scale(1.1) rotate(5deg);
}

.icon {
  font-size: 2rem;
  filter: grayscale(20%);
  transition: filter 0.3s ease;
}

.feature-card:hover .icon {
  filter: grayscale(0%);
}

.feature-content {
  text-align: center;
}

.feature-content h3 {
  font-size: 1.375rem;
  font-weight: 600;
  color: #1e293b;
  margin-bottom: 0.75rem;
  line-height: 1.3;
}

.feature-content p {
  color: #64748b;
  line-height: 1.6;
  font-size: 0.95rem;
  margin: 0;
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

.feature-card {
  animation: fadeInUp 0.6s ease-out;
}

.feature-card:nth-child(1) { animation-delay: 0.1s; }
.feature-card:nth-child(2) { animation-delay: 0.2s; }
.feature-card:nth-child(3) { animation-delay: 0.3s; }
.feature-card:nth-child(4) { animation-delay: 0.4s; }

/* Mobile Responsive */
@media (max-width: 768px) {
  .features {
    padding: 3rem 1rem;
  }
  
  .section-header h2 {
    font-size: 2.25rem;
  }
  
  .section-header p {
    font-size: 1rem;
  }
  
  .features-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .feature-card {
    padding: 2rem 1.5rem;
  }
  
  .icon-wrapper {
    width: 70px;
    height: 70px;
  }
  
  .icon {
    font-size: 1.75rem;
  }
  
  .feature-content h3 {
    font-size: 1.25rem;
  }
}

@media (max-width: 480px) {
  .features {
    padding: 2rem 1rem;
  }
  
  .section-header h2 {
    font-size: 2rem;
  }
  
  .feature-card {
    padding: 1.5rem 1rem;
  }
  
  .icon-wrapper {
    width: 60px;
    height: 60px;
  }
  
  .icon {
    font-size: 1.5rem;
  }
}

/* Hover effect for mouse tracking */
.feature-card {
  --mouse-x: 50%;
  --mouse-y: 50%;
}
</style>