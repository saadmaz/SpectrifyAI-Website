<script setup lang="ts">
import { ref } from 'vue'

const expandedFAQ = ref<number | null>(null)

const faqItems = [
  {
    question: 'How fast does the SpectrifyAI system analyze samples?',
    answer: 'SpectrifyAI completes a full analysis in under 2 minutes per sample, including calibration and result generation. This is 8-10x faster than traditional lab methods.'
  },
  {
    question: 'What is the accuracy of the AI model?',
    answer: 'Our AI models achieve 99.9% accuracy in quality classification and 98.7% precision in adulteration detection, validated against ISO 17025 standards and independent lab testing.'
  },
  {
    question: 'Can SpectrifyAI detect all types of adulteration?',
    answer: 'SpectrifyAI can detect the most common adulterants including added sugars, synthetic colorants, moisture problems, and inferior substitutes. We continuously update our models for new fraud patterns.'
  },
  {
    question: 'How much does SpectrifyAI cost?',
    answer: 'Pricing depends on your testing volume and deployment model. Most customers see ROI within 12 months. Contact our sales team for a custom quote based on your needs.'
  },
  {
    question: 'Does SpectrifyAI integrate with our existing systems?',
    answer: 'Yes! We provide REST APIs for integration with LIMS, ERP, and QMS systems. Our technical team can work with your IT department to ensure seamless integration.'
  },
  {
    question: 'What support do you provide?',
    answer: 'We offer 24/7 email support, phone support during business hours, comprehensive documentation, video tutorials, and optional on-site training for your team.'
  },
  {
    question: 'Is my data secure with SpectrifyAI?',
    answer: 'Yes. We use bank-level AES-256 encryption, GDPR compliance, SOC 2 certification, and role-based access control. Your data never trains public models.'
  },
  {
    question: 'Can I use SpectrifyAI in the field or only in a lab?',
    answer: 'Our spectrometer is portable and field-ready (IP65 rated). Many customers use it for incoming shipment verification, field testing, and even source verification at origins.'
  }
]

const toggleFAQ = (index: number) => {
  expandedFAQ.value = expandedFAQ.value === index ? null : index
}
</script>

<template>
  <div class="support-page">
    <section class="hero">
      <div class="container">
        <h1>Support & Resources</h1>
        <p class="hero-subtitle">
          Comprehensive documentation, live support, and resources to help you succeed with SpectrifyAI.
        </p>
      </div>
    </section>

    <section class="section support-channels-section">
      <div class="container">
        <h2 class="section-title">How Can We Help?</h2>
        <div class="channels-grid">
          <a href="#contact" class="channel-card">
            <div class="channel-icon">💬</div>
            <h3>Live Chat</h3>
            <p>Instant answers to common questions. Available 24/7</p>
          </a>
          <a href="#contact" class="channel-card">
            <div class="channel-icon">📧</div>
            <h3>Email Support</h3>
            <p>support@spectrifyai.com. Response within 2 hours</p>
          </a>
          <a href="#contact" class="channel-card">
            <div class="channel-icon">☎️</div>
            <h3>Phone Support</h3>
            <p>+1 (555) SPECTRIFY. Mon-Fri, 8am-6pm PT</p>
          </a>
          <a href="#contact" class="channel-card">
            <div class="channel-icon">🎓</div>
            <h3>Training Programs</h3>
            <p>On-site and virtual training for your team</p>
          </a>
        </div>
      </div>
    </section>

    <section class="section documentation-section">
      <div class="container">
        <h2 class="section-title">Documentation & Guides</h2>
        <div class="docs-grid">
          <div class="doc-category">
            <h3>Getting Started</h3>
            <ul>
              <li><a href="#">Unboxing & Setup Guide</a></li>
              <li><a href="#">Initial Calibration</a></li>
              <li><a href="#">First Sample Analysis</a></li>
              <li><a href="#">Understanding Results</a></li>
            </ul>
          </div>
          <div class="doc-category">
            <h3>Technical Documentation</h3>
            <ul>
              <li><a href="#">API Reference</a></li>
              <li><a href="#">Data Format Specifications</a></li>
              <li><a href="#">System Integration Guide</a></li>
              <li><a href="#">Security & Compliance</a></li>
            </ul>
          </div>
          <div class="doc-category">
            <h3>Best Practices</h3>
            <ul>
              <li><a href="#">Sample Preparation</a></li>
              <li><a href="#">Quality Control Workflows</a></li>
              <li><a href="#">Maintenance & Troubleshooting</a></li>
              <li><a href="#">Data Management</a></li>
            </ul>
          </div>
          <div class="doc-category">
            <h3>Industry Guides</h3>
            <ul>
              <li><a href="#">Tea Quality Standards</a></li>
              <li><a href="#">Spice Authenticity Testing</a></li>
              <li><a href="#">Herb Potency Verification</a></li>
              <li><a href="#">Compliance & Regulations</a></li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <section id="faq" class="section faq-section">
      <div class="container">
        <h2 class="section-title">Frequently Asked Questions</h2>
        <div class="faq-container">
          <div
            v-for="(item, index) in faqItems"
            :key="index"
            class="faq-item"
            :class="{ expanded: expandedFAQ === index }"
          >
            <button class="faq-question" @click="toggleFAQ(index)">
              <span>{{ item.question }}</span>
              <span class="faq-toggle">+</span>
            </button>
            <div class="faq-answer">
              <p>{{ item.answer }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section resources-section">
      <div class="container">
        <h2 class="section-title">Additional Resources</h2>
        <div class="resources-grid">
          <div class="resource-card">
            <div class="resource-icon">📹</div>
            <h3>Video Tutorials</h3>
            <p>Step-by-step video guides for common tasks and workflows</p>
            <a href="#" class="resource-link">Watch Videos →</a>
          </div>
          <div class="resource-card">
            <div class="resource-icon">📚</div>
            <h3>Webinars & Workshops</h3>
            <p>Live sessions covering advanced features and best practices</p>
            <a href="#" class="resource-link">View Schedule →</a>
          </div>
          <div class="resource-card">
            <div class="resource-icon">🔬</div>
            <h3>Research & Studies</h3>
            <p>White papers and validation studies demonstrating accuracy</p>
            <a href="#" class="resource-link">Download PDFs →</a>
          </div>
          <div class="resource-card">
            <div class="resource-icon">🤝</div>
            <h3>Community Forum</h3>
            <p>Connect with other SpectrifyAI users and share best practices</p>
            <a href="#" class="resource-link">Join Forum →</a>
          </div>
        </div>
      </div>
    </section>

    <section class="section troubleshooting-section">
      <div class="container">
        <h2 class="section-title">Troubleshooting</h2>
        <div class="troubleshooting-grid">
          <div class="troubleshooting-card">
            <h3>Device Not Connecting</h3>
            <ul>
              <li>Check WiFi connection</li>
              <li>Restart the device</li>
              <li>Update firmware to latest version</li>
              <li>Check firewall settings</li>
            </ul>
          </div>
          <div class="troubleshooting-card">
            <h3>Unexpected Results</h3>
            <ul>
              <li>Verify sample preparation</li>
              <li>Clean the sensor</li>
              <li>Recalibrate the device</li>
              <li>Contact support with sample details</li>
            </ul>
          </div>
          <div class="troubleshooting-card">
            <h3>Integration Issues</h3>
            <ul>
              <li>Verify API credentials</li>
              <li>Check network connectivity</li>
              <li>Review error logs</li>
              <li>Contact technical support</li>
            </ul>
          </div>
          <div class="troubleshooting-card">
            <h3>Software Problems</h3>
            <ul>
              <li>Clear app cache</li>
              <li>Reinstall the application</li>
              <li>Check system requirements</li>
              <li>Submit bug report</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <section id="contact" class="section contact-section">
      <div class="container">
        <h2 class="section-title">Get in Touch</h2>
        <div class="contact-grid">
          <div class="contact-form-box">
            <h3>Send us a Message</h3>
            <form class="contact-form">
              <div class="form-group">
                <label for="name">Full Name</label>
                <input type="text" id="name" name="name" placeholder="Your name" required />
              </div>
              <div class="form-group">
                <label for="email">Email Address</label>
                <input type="email" id="email" name="email" placeholder="you@company.com" required />
              </div>
              <div class="form-group">
                <label for="subject">Subject</label>
                <input type="text" id="subject" name="subject" placeholder="How can we help?" required />
              </div>
              <div class="form-group">
                <label for="message">Message</label>
                <textarea id="message" name="message" rows="5" placeholder="Tell us more..." required></textarea>
              </div>
              <button type="submit" class="btn btn-primary">Send Message</button>
            </form>
          </div>

          <div class="contact-info-box">
            <h3>Contact Information</h3>
            <div class="contact-item">
              <h4>Support Email</h4>
              <a href="mailto:support@spectrifyai.com">support@spectrifyai.com</a>
            </div>
            <div class="contact-item">
              <h4>Sales Inquiries</h4>
              <a href="mailto:sales@spectrifyai.com">sales@spectrifyai.com</a>
            </div>
            <div class="contact-item">
              <h4>Phone</h4>
              <a href="tel:+1-555-0123">+1 (555) SPECTRIFY</a>
            </div>
            <div class="contact-item">
              <h4>Hours</h4>
              <p>Monday - Friday, 8am - 6pm PT</p>
            </div>
            <div class="contact-item">
              <h4>Office Location</h4>
              <p>San Francisco, CA, USA</p>
            </div>
            <div class="contact-item">
              <h4>Emergency Support</h4>
              <p>Available 24/7 for critical issues</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section sla-section">
      <div class="container">
        <h2 class="section-title">Service Level Agreements</h2>
        <div class="sla-table">
          <div class="sla-header">
            <div class="sla-col">Priority Level</div>
            <div class="sla-col">Response Time</div>
            <div class="sla-col">Resolution Time</div>
          </div>
          <div class="sla-row">
            <div class="sla-col">Critical</div>
            <div class="sla-col">1 hour</div>
            <div class="sla-col">4 hours</div>
          </div>
          <div class="sla-row">
            <div class="sla-col">High</div>
            <div class="sla-col">2 hours</div>
            <div class="sla-col">8 hours</div>
          </div>
          <div class="sla-row">
            <div class="sla-col">Medium</div>
            <div class="sla-col">4 hours</div>
            <div class="sla-col">24 hours</div>
          </div>
          <div class="sla-row">
            <div class="sla-col">Low</div>
            <div class="sla-col">24 hours</div>
            <div class="sla-col">72 hours</div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.support-page {
  width: 100%;
}

.hero {
  background: linear-gradient(135deg, var(--color-primary), var(--color-primary-light));
  color: white;
  padding: 6rem 2rem 4rem;
  text-align: center;
}

.hero h1 {
  color: white;
  margin-bottom: 1.5rem;
}

.hero-subtitle {
  font-size: 1.25rem;
  color: rgba(255, 255, 255, 0.9);
  max-width: 800px;
  margin: 0 auto;
}

.support-channels-section {
  background: var(--color-bg);
}

.channels-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.channel-card {
  background: white;
  padding: 2.5rem;
  border-radius: 12px;
  text-decoration: none;
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
}

.channel-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12);
}

.channel-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.channel-card h3 {
  color: var(--color-primary);
  margin-bottom: 0.75rem;
}

.channel-card p {
  color: var(--color-text-light);
}

.documentation-section {
  background: white;
}

.docs-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.doc-category {
  background: var(--color-bg);
  padding: 2rem;
  border-radius: 12px;
}

.doc-category h3 {
  color: var(--color-primary);
  margin-bottom: 1.5rem;
  font-size: 1.1rem;
}

.doc-category ul {
  list-style: none;
  padding: 0;
}

.doc-category li {
  margin-bottom: 1rem;
}

.doc-category a {
  color: var(--color-primary);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.doc-category a:hover {
  color: var(--color-primary-light);
  text-decoration: underline;
}

.faq-section {
  background: var(--color-bg);
}

.faq-container {
  max-width: 900px;
  margin: 0 auto;
}

.faq-item {
  background: white;
  border-radius: 12px;
  margin-bottom: 1rem;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  transition: box-shadow 0.3s ease;
}

.faq-item:hover,
.faq-item.expanded {
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.1);
}

.faq-question {
  width: 100%;
  padding: 1.5rem 2rem;
  background: white;
  border: none;
  text-align: left;
  font-size: 1rem;
  font-weight: 600;
  color: var(--color-primary);
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
  transition: background 0.3s ease;
}

.faq-question:hover {
  background: var(--color-bg);
}

.faq-toggle {
  font-size: 1.5rem;
  transition: transform 0.3s ease;
}

.faq-item.expanded .faq-toggle {
  transform: rotate(45deg);
}

.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease;
  background: var(--color-bg);
}

.faq-item.expanded .faq-answer {
  max-height: 500px;
}

.faq-answer p {
  padding: 1.5rem 2rem;
  color: var(--color-text-light);
  line-height: 1.7;
  margin: 0;
}

.resources-section {
  background: white;
}

.resources-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.resource-card {
  background: var(--color-bg);
  padding: 2rem;
  border-radius: 12px;
  text-align: center;
}

.resource-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.resource-card h3 {
  color: var(--color-primary);
  margin-bottom: 1rem;
}

.resource-card p {
  color: var(--color-text-light);
  margin-bottom: 1.5rem;
}

.resource-link {
  display: inline-block;
  color: var(--color-primary);
  font-weight: 600;
  text-decoration: none;
  transition: color 0.3s ease;
}

.resource-link:hover {
  color: var(--color-primary-light);
}

.troubleshooting-section {
  background: var(--color-bg);
}

.troubleshooting-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.troubleshooting-card {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.troubleshooting-card h3 {
  color: var(--color-primary);
  margin-bottom: 1rem;
  font-size: 1.1rem;
}

.troubleshooting-card ul {
  list-style: none;
  padding: 0;
}

.troubleshooting-card li {
  padding: 0.5rem 0;
  padding-left: 1.5rem;
  position: relative;
  color: var(--color-text-light);
}

.troubleshooting-card li::before {
  content: '→';
  position: absolute;
  left: 0;
  color: var(--color-primary);
  font-weight: bold;
}

.contact-section {
  background: white;
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
}

.contact-form-box h3,
.contact-info-box h3 {
  color: var(--color-primary);
  margin-bottom: 2rem;
  font-size: 1.3rem;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.form-group label {
  font-weight: 600;
  color: var(--color-text);
}

.form-group input,
.form-group textarea {
  padding: 0.75rem 1rem;
  border: 2px solid var(--color-bg);
  border-radius: 8px;
  font-family: inherit;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--color-primary);
}

.contact-info-box {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.contact-item h4 {
  color: var(--color-primary);
  margin-bottom: 0.5rem;
}

.contact-item p,
.contact-item a {
  color: var(--color-text-light);
  text-decoration: none;
}

.contact-item a:hover {
  text-decoration: underline;
  color: var(--color-primary);
}

.sla-section {
  background: var(--color-bg);
}

.sla-table {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
}

.sla-header {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  background: var(--color-primary);
  color: white;
  font-weight: 700;
  padding: 1.5rem;
  gap: 2rem;
}

.sla-row {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  padding: 1.5rem;
  gap: 2rem;
  border-bottom: 1px solid var(--color-bg);
}

.sla-row:last-child {
  border-bottom: none;
}

.sla-col {
  color: var(--color-text);
}

@media (max-width: 968px) {
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .sla-header,
  .sla-row {
    grid-template-columns: 1fr;
    gap: 1rem;
  }

  .sla-col::before {
    content: attr(data-label);
    font-weight: 700;
    color: var(--color-primary);
  }
}
</style>
