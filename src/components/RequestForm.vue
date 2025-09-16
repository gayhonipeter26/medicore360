<template>
  <div class="overlay" @click.self="$emit('close')">
    <div class="form-card">
      <div class="form-header">
        <div class="header-icon">
          <div class="medical-cross">
            <div class="cross-horizontal"></div>
            <div class="cross-vertical"></div>
          </div>
        </div>
        <h2>Request an Account</h2>
        <p>Join thousands of healthcare professionals using MediCore360</p>
        <button class="close-btn" @click="$emit('close')">
          <span>&times;</span>
        </button>
      </div>

      <form @submit.prevent="submitForm" class="account-form">
        <div class="form-group">
          <label for="name">Full Name</label>
          <div class="input-wrapper">
            <input 
              id="name"
              type="text" 
              v-model="form.name" 
              placeholder="Enter your full name" 
              required 
              class="form-input"
            />
            <span class="input-icon">👤</span>
          </div>
        </div>

        <div class="form-group">
          <label for="email">Work Email</label>
          <div class="input-wrapper">
            <input 
              id="email"
              type="email" 
              v-model="form.email" 
              placeholder="your.email@hospital.com" 
              required 
              class="form-input"
            />
            <span class="input-icon">✉️</span>
          </div>
        </div>

        <div class="form-row">
          <div class="form-group">
            <label for="phone">Phone Number</label>
            <div class="input-wrapper">
              <input 
                id="phone"
                type="tel" 
                v-model="form.phone" 
                placeholder="+1 (555) 000-0000" 
                required 
                class="form-input"
              />
              <span class="input-icon">📞</span>
            </div>
          </div>

          <div class="form-group">
            <label for="userType">Your Role</label>
            <div class="select-wrapper">
              <select id="userType" v-model="form.userType" required class="form-select">
                <option disabled value="">Select your role</option>
                <option>Doctor</option>
                <option>Nurse</option>
                <option>Pharmacist</option>
                <option>Lab Technician</option>
                <option>Administrator</option>
                <option>Other</option>
              </select>
              <span class="select-arrow">⌄</span>
            </div>
          </div>
        </div>

        <div class="form-group">
          <label for="organization">Hospital/Clinic Name</label>
          <div class="input-wrapper">
            <input 
              id="organization"
              type="text" 
              v-model="form.organization" 
              placeholder="Enter your organization name" 
              required 
              class="form-input"
            />
            <span class="input-icon">🏥</span>
          </div>
        </div>

        <div class="form-group">
          <label for="reason">Why do you need an account?</label>
          <textarea 
            id="reason"
            v-model="form.reason" 
            placeholder="Briefly describe how you plan to use MediCore360 in your healthcare facility..."
            required 
            class="form-textarea"
            rows="4"
          ></textarea>
        </div>

        <div class="form-actions">
          <button type="submit" class="submit-btn" :disabled="isSubmitting">
            <span v-if="!isSubmitting">Submit Request</span>
            <span v-else class="loading">
              <span class="spinner"></span>
              Processing...
            </span>
          </button>
          <button type="button" @click="$emit('close')" class="cancel-btn">
            Cancel
          </button>
        </div>
      </form>

      <div class="form-footer">
        <p>
          <span class="security-icon">🔒</span>
          Your information is secure and will only be used for account verification
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from "vue";

const isSubmitting = ref(false);

const form = reactive({
  name: "",
  email: "",
  phone: "",
  organization: "",
  userType: "",
  reason: "",
});

const submitForm = async () => {
  isSubmitting.value = true;
  
  // Simulate API call
  await new Promise(resolve => setTimeout(resolve, 2000));
  
  alert(`🎉 Request submitted successfully!\n\nThank you, ${form.name}. We'll review your request and get back to you within 24 hours at ${form.email}.`);
  
  // Reset form
  Object.keys(form).forEach(key => {
    form[key] = "";
  });
  
  isSubmitting.value = false;
};
</script>

<style scoped>
.overlay {
  position: fixed;
  inset: 0;
  background: rgba(15, 23, 42, 0.7);
  backdrop-filter: blur(8px);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
  padding: 1rem;
  animation: fadeIn 0.3s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.form-card {
  background: white;
  border-radius: 24px;
  width: 100%;
  max-width: 520px;
  max-height: 90vh;
  overflow-y: auto;
  box-shadow: 0 25px 60px rgba(0, 0, 0, 0.2);
  position: relative;
  animation: slideUp 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  /* Hide scrollbar */
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: none; /* Internet Explorer 10+ */
}

.form-card::-webkit-scrollbar {
  display: none; /* Safari and Chrome */
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(20px) scale(0.95);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.form-header {
  background: linear-gradient(135deg, #1e40af 0%, #3b82f6 100%);
  color: white;
  padding: 2rem;
  border-radius: 24px 24px 0 0;
  text-align: center;
  position: relative;
}

.header-icon {
  width: 60px;
  height: 60px;
  background: rgba(255, 255, 255, 0.15);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1rem;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.medical-cross {
  position: relative;
  width: 24px;
  height: 24px;
}

.cross-horizontal,
.cross-vertical {
  position: absolute;
  background: white;
  border-radius: 2px;
}

.cross-horizontal {
  width: 20px;
  height: 4px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.cross-vertical {
  width: 4px;
  height: 20px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.form-header h2 {
  margin: 0 0 0.5rem 0;
  font-size: 1.75rem;
  font-weight: 700;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.form-header p {
  margin: 0;
  font-size: 0.95rem;
  opacity: 0.9;
  font-weight: 400;
}

.close-btn {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background: rgba(255, 255, 255, 0.2);
  border: none;
  color: white;
  width: 40px;
  height: 40px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.2s ease;
  backdrop-filter: blur(10px);
}

.close-btn:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: scale(1.05);
}

.close-btn span {
  font-size: 1.5rem;
  line-height: 1;
}

.account-form {
  padding: 2rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.form-group label {
  display: block;
  font-weight: 600;
  color: #374151;
  margin-bottom: 0.5rem;
  font-size: 0.875rem;
  letter-spacing: 0.01em;
}

.input-wrapper,
.select-wrapper {
  position: relative;
}

.form-input,
.form-select,
.form-textarea {
  width: 100%;
  padding: 1rem 1rem 1rem 3rem;
  border: 2px solid #e5e7eb;
  border-radius: 12px;
  font-size: 0.95rem;
  transition: all 0.3s ease;
  background: #fafafa;
  color: #374151;
  box-sizing: border-box;
}

.form-textarea {
  padding: 1rem;
  resize: vertical;
  font-family: inherit;
  min-height: 100px;
}

.form-input:focus,
.form-select:focus,
.form-textarea:focus {
  outline: none;
  border-color: #3b82f6;
  background: white;
  box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
}

.input-icon {
  position: absolute;
  left: 1rem;
  top: 50%;
  transform: translateY(-50%);
  font-size: 1rem;
  opacity: 0.6;
  pointer-events: none;
}

.select-wrapper {
  position: relative;
}

.form-select {
  appearance: none;
  cursor: pointer;
  padding-right: 3rem;
}

.select-arrow {
  position: absolute;
  right: 1rem;
  top: 50%;
  transform: translateY(-50%);
  font-size: 1.2rem;
  color: #6b7280;
  pointer-events: none;
}

.form-actions {
  display: flex;
  gap: 1rem;
  margin-top: 2rem;
}

.submit-btn {
  flex: 1;
  background: linear-gradient(135deg, #3b82f6 0%, #1d4ed8 100%);
  color: white;
  border: none;
  padding: 1rem 2rem;
  border-radius: 12px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
}

.submit-btn:hover:not(:disabled) {
  background: linear-gradient(135deg, #1d4ed8 0%, #1e40af 100%);
  transform: translateY(-1px);
  box-shadow: 0 8px 25px rgba(59, 130, 246, 0.4);
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
  transform: none;
}

.loading {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.spinner {
  width: 16px;
  height: 16px;
  border: 2px solid rgba(255, 255, 255, 0.3);
  border-top: 2px solid white;
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

.cancel-btn {
  background: #f3f4f6;
  color: #6b7280;
  border: 2px solid #e5e7eb;
  padding: 1rem 2rem;
  border-radius: 12px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.cancel-btn:hover {
  background: #e5e7eb;
  color: #374151;
}

.form-footer {
  padding: 1.5rem 2rem;
  background: #f8fafc;
  border-radius: 0 0 24px 24px;
  border-top: 1px solid #e5e7eb;
}

.form-footer p {
  margin: 0;
  font-size: 0.8rem;
  color: #6b7280;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  justify-content: center;
}

.security-icon {
  font-size: 0.9rem;
}

/* Mobile Responsive */
@media (max-width: 768px) {
  .overlay {
    padding: 0.5rem;
  }
  
  .form-card {
    max-width: 100%;
    border-radius: 16px;
  }
  
  .form-header {
    padding: 1.5rem;
    border-radius: 16px 16px 0 0;
  }
  
  .form-header h2 {
    font-size: 1.5rem;
  }
  
  .account-form {
    padding: 1.5rem;
  }
  
  .form-row {
    grid-template-columns: 1fr;
    gap: 0;
  }
  
  .form-actions {
    flex-direction: column;
  }
  
  .form-footer {
    padding: 1rem 1.5rem;
  }
}

@media (max-width: 480px) {
  .form-header {
    padding: 1rem;
  }
  
  .account-form {
    padding: 1rem;
  }
  
  .form-input,
  .form-select,
  .form-textarea {
    padding: 0.875rem 0.875rem 0.875rem 2.5rem;
  }
  
  .input-icon {
    left: 0.75rem;
    font-size: 0.9rem;
  }
}</style>