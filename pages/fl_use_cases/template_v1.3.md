---
version: 1.3
search_exclude: false
toc: false
description: A practical implementation guide for federated analytics projects, inspired by the FL lifecycle
---

<style>
/* Professional, production-grade design */
:root {
  --primary-color: #2563eb;
  --secondary-color: #1e40af;
  --accent-color: #f59e0b;
  --success-color: #059669;
  --warning-color: #d97706;
  --danger-color: #dc2626;
  --text-primary: #111827;
  --text-secondary: #6b7280;
  --text-muted: #9ca3af;
  --bg-light: #f9fafb;
  --bg-white: #ffffff;
  --border-color: #e5e7eb;
  --border-light: #f3f4f6;
  --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

/* Header Section - Clean and Simple */
.template-header {
  background: #ffffff;
  color: #1f2937;
  padding: 32px 0;
  margin: 0 0 24px 0;
  border-bottom: 1px solid #e5e7eb;
}

.template-title {
  font-size: 2.2em;
  font-weight: 600;
  margin: 0 0 12px 0;
  line-height: 1.2;
  color: #1f2937;
}

.template-subtitle {
  font-size: 1.1em;
  margin: 0 0 16px 0;
  line-height: 1.5;
  max-width: 100%;
  font-weight: 400;
  color: #4b5563;
}

.template-description {
  font-size: 1em;
  margin: 0;
  line-height: 1.6;
  max-width: 100%;
  font-weight: 300;
  color: #6b7280;
}

/* General Disclaimer */
.general-disclaimer {
  background: #fef3c7;
  border: 1px solid #f59e0b;
  border-left: 4px solid #d97706;
  padding: 20px;
  margin: 20px 0;
  border-radius: 8px;
  font-size: 0.95em;
  color: #92400e;
  max-width: 100%;
}

.general-disclaimer strong {
  color: #78350f;
}

.general-disclaimer p {
  margin: 0 0 12px 0;
  line-height: 1.5;
}

.general-disclaimer p:last-child {
  margin-bottom: 0;
}

/* Beginner Guide Section - Professional Academic Design */
.beginner-guide {
  background: #ffffff;
  border: 1px solid #e5e7eb;
  border-left: 4px solid #374151;
  padding: 24px;
  margin: 32px 0;
  box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1);
}

.beginner-header {
  margin-bottom: 16px;
}

.beginner-icon {
  display: none;
}

.beginner-title {
  font-size: 1.3em;
  font-weight: 600;
  color: #374151;
  margin: 0;
  border-bottom: 1px solid #e5e7eb;
  padding-bottom: 8px;
}

.beginner-content {
  color: var(--text-secondary);
  line-height: 1.7;
}

.beginner-content p {
  font-size: 1.1em;
  margin-bottom: 20px;
}

.beginner-content ol {
  margin: 16px 0;
  padding-left: 20px;
}

.beginner-content li {
  margin: 8px 0;
  color: #374151;
  line-height: 1.6;
}

.beginner-content a {
  color: #7c3aed;
  text-decoration: none;
  font-weight: 600;
  border-bottom: 2px solid transparent;
  transition: all 0.3s ease;
}

.beginner-content a:hover {
  border-bottom-color: #7c3aed;
  transform: translateY(-1px);
}

.beginner-highlights {
  margin: 24px 0;
  display: grid;
  gap: 20px;
}

.highlight-item {
  display: flex;
  gap: 16px;
  padding: 20px;
  background: #f8fafc;
  border: 1px solid #e2e8f0;
  border-radius: 8px;
  transition: all 0.2s ease;
}

.highlight-item:hover {
  background: #f1f5f9;
  border-color: #cbd5e1;
  transform: translateY(-1px);
}

.highlight-icon {
  font-size: 1.5em;
  flex-shrink: 0;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #e0e7ff;
  border-radius: 8px;
}

.highlight-content {
  flex: 1;
}

.highlight-content strong {
  display: block;
  color: #374151;
  font-size: 1em;
  margin-bottom: 8px;
  font-weight: 600;
}

.highlight-content p {
  margin: 0;
  color: #4b5563;
  font-size: 0.95em;
  line-height: 1.6;
}

.beginner-resources {
  margin-top: 32px;
  padding: 24px;
  background: #f9fafb;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
}

.beginner-resources h4 {
  color: #374151;
  font-size: 1.1em;
  font-weight: 600;
  margin: 0 0 20px 0;
  display: flex;
  align-items: center;
  gap: 8px;
}

.resource-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}

.resource-item {
  padding: 16px;
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 6px;
  transition: all 0.2s ease;
}

.resource-item:hover {
  border-color: #7c3aed;
  box-shadow: 0 2px 8px rgba(124, 58, 237, 0.1);
}

.resource-item strong {
  display: block;
  color: #374151;
  font-size: 0.95em;
  margin-bottom: 8px;
  font-weight: 600;
}

.resource-item p {
  margin: 0;
  color: #4b5563;
  font-size: 0.9em;
  line-height: 1.5;
}

.beginner-note {
  background: #f9fafb;
  border: 1px solid #e5e7eb;
  border-left: 3px solid #6b7280;
  padding: 16px;
  margin-top: 16px;
  font-size: 0.95em;
}

.pro-tip-header {
  margin-bottom: 8px;
}

.pro-tip-icon {
  display: none;
}

.beginner-note p {
  margin: 0;
  color: #4b5563;
  line-height: 1.5;
}

.extended-version {
  background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%);
  border: 1px solid #f59e0b;
  border-left: 4px solid #d97706;
  padding: 24px;
  margin: 32px 0;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(245, 158, 11, 0.1);
  position: relative;
  overflow: hidden;
}

.extended-version::before {
  content: '📚';
  position: absolute;
  top: 20px;
  right: 20px;
  font-size: 1.5em;
  opacity: 0.3;
}

.extended-header {
  color: #92400e;
  font-weight: 700;
  margin: 0 0 12px 0;
  font-size: 1.2em;
}

.extended-icon {
  display: none;
}

.extended-version p {
  color: #78350f;
  font-size: 1em;
  margin: 0;
  line-height: 1.6;
}

.extended-version a {
  color: #d97706;
  text-decoration: none;
  font-weight: 600;
  border-bottom: 2px solid #d97706;
  transition: all 0.2s ease;
}

.extended-version a:hover {
  color: #b45309;
  border-bottom-color: #b45309;
}

/* Steps Introduction Section */
.steps-intro {
  background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
  border: 1px solid #e2e8f0;
  border-radius: 12px;
  padding: 32px;
  margin: 32px 0;
  text-align: center;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.steps-intro h2 {
  color: #1f2937;
  font-size: 1.8em;
  font-weight: 700;
  margin: 0 0 16px 0;
  line-height: 1.2;
}

.steps-intro p {
  color: #4b5563;
  font-size: 1.1em;
  line-height: 1.6;
  margin: 0 0 16px 0;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
}

.steps-intro p:last-child {
  margin-bottom: 0;
  font-size: 1em;
  color: #6b7280;
}

/* Steps Overview Section */
.steps-overview {
  margin: 32px 0;
}

.steps-header {
  text-align: center;
  margin-bottom: 24px;
}

.steps-title {
  font-size: 1.5em;
  font-weight: 600;
  color: var(--text-primary);
  margin: 0 0 8px 0;
}

.steps-subtitle {
  color: var(--text-secondary);
  font-size: 0.95em;
}

.steps-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 32px;
  margin: 40px 0;
  position: relative;
}

.steps-grid::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 2px;
  height: 80%;
  background: linear-gradient(to bottom, transparent, #7c3aed, #8b5cf6, #a855f7, transparent);
  opacity: 0.3;
  z-index: 0;
}

.steps-grid::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 1px;
  height: 60%;
  background: linear-gradient(to bottom, transparent, rgba(124, 58, 237, 0.1), rgba(139, 92, 246, 0.1), transparent);
  z-index: 0;
}

.step-card {
  background: linear-gradient(135deg, #ffffff 0%, #fafafa 100%);
  border: 1px solid #e5e7eb;
  border-left: 6px solid #6b7280;
  border-radius: 12px;
  padding: 32px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  cursor: pointer;
  min-height: 320px;
  position: relative;
  overflow: hidden;
}

.step-card::before {
  content: '';
  position: absolute;
  top: 0;
  right: 0;
  width: 100px;
  height: 100px;
  background: linear-gradient(135deg, rgba(107, 114, 128, 0.05), rgba(107, 114, 128, 0.02));
  border-radius: 0 12px 0 100px;
  z-index: 0;
}

.step-card:hover {
  border-left-color: #4b5563;
  box-shadow: 0 8px 25px rgba(107, 114, 128, 0.08);
  transform: translateY(-4px) scale(1.02);
}

.step-card:hover::before {
  background: linear-gradient(135deg, rgba(107, 114, 128, 0.08), rgba(107, 114, 128, 0.04));
}

.step-header {
  display: flex;
  align-items: baseline;
  gap: 16px;
  margin-bottom: 16px;
  position: relative;
  z-index: 1;
}

.step-icon {
  font-size: 1.2em;
  width: 52px;
  height: 52px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #6b7280, #9ca3af);
  color: white;
  border-radius: 16px;
  flex-shrink: 0;
  font-weight: 700;
  box-shadow: 0 4px 12px rgba(107, 114, 128, 0.15);
  position: relative;
  transition: all 0.3s ease;
  margin-top: -6px;
}

.step-icon::after {
  content: '';
  position: absolute;
  inset: -2px;
  background: linear-gradient(135deg, #6b7280, #9ca3af, #d1d5db);
  border-radius: 18px;
  z-index: -1;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.step-card:hover .step-icon::after {
  opacity: 1;
}

.step-info {
  flex: 1;
  position: relative;
  z-index: 1;
}

.step-info h2 {
  margin: 0 0 6px 0;
  font-size: 1.3em;
  font-weight: 700;
  color: #1f2937;
  line-height: 1.2;
}

.step-number {
  font-size: 0.8em;
  color: #6b7280;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.step-description {
  color: #4b5563;
  font-size: 0.95em;
  line-height: 1.6;
  margin-bottom: 20px;
  position: relative;
  z-index: 1;
}

.step-key-points {
  margin: 16px 0;
  position: relative;
  z-index: 1;
}

.step-key-points ul {
  margin: 0;
  padding-left: 20px;
  list-style: none;
}

.step-key-points li {
  color: #6b7280;
  font-size: 0.9em;
  margin: 6px 0;
  position: relative;
  padding-left: 8px;
}

.step-key-points li::before {
  content: "▶";
  color: #6b7280;
  font-weight: bold;
  position: absolute;
  left: -20px;
  font-size: 0.8em;
}

.step-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 0.8em;
  color: #6b7280;
  padding-top: 16px;
  border-top: 1px solid #e5e7eb;
  margin-top: 12px;
  position: relative;
  z-index: 1;
}

.step-meta-left {
  display: flex;
  gap: 12px;
}

.step-meta-item {
  display: flex;
  align-items: center;
  gap: 4px;
  font-weight: 500;
}

.step-meta-icon {
  font-size: 0.9em;
}

.step-difficulty {
  padding: 6px 12px;
  border-radius: 20px;
  font-size: 0.75em;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  background: linear-gradient(135deg, #f3f4f6, #e5e7eb);
  color: #374151;
  border: 1px solid #d1d5db;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  transition: all 0.2s ease;
}

.step-card:hover .step-difficulty {
  background: linear-gradient(135deg, #6b7280, #9ca3af);
  color: white;
  border-color: #4b5563;
  box-shadow: 0 2px 6px rgba(107, 114, 128, 0.15);
}

/* Role link hover effects */
.step-meta a:hover {
  color: #4b5563 !important;
  text-decoration: underline !important;
}

/* Subtle animation for step cards */
@keyframes stepCardFloat {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-2px); }
}

.step-card:nth-child(1) {
  animation: stepCardFloat 6s ease-in-out infinite;
  animation-delay: 0s;
}

.step-card:nth-child(2) {
  animation: stepCardFloat 6s ease-in-out infinite;
  animation-delay: 1.5s;
}

.step-card:nth-child(3) {
  animation: stepCardFloat 6s ease-in-out infinite;
  animation-delay: 3s;
}

.step-card:nth-child(4) {
  animation: stepCardFloat 6s ease-in-out infinite;
  animation-delay: 4.5s;
}

/* Flow indicators between cards */
.step-card-1::after {
  content: '→';
  position: absolute;
  right: -20px;
  top: 50%;
  transform: translateY(-50%);
  color: #7c3aed;
  font-size: 1.5em;
  font-weight: bold;
  opacity: 0.6;
  z-index: 10;
}

.step-card-2::after {
  content: '↓';
  position: absolute;
  bottom: -20px;
  left: 50%;
  transform: translateX(-50%);
  color: #7c3aed;
  font-size: 1.5em;
  font-weight: bold;
  opacity: 0.6;
  z-index: 10;
}

.step-card-3::after {
  content: '←';
  position: absolute;
  left: -20px;
  top: 50%;
  transform: translateY(-50%);
  color: #7c3aed;
  font-size: 1.5em;
  font-weight: bold;
  opacity: 0.6;
  z-index: 10;
}

/* Hide flow indicators on hover for cleaner look */
.step-card:hover::after {
  opacity: 0;
}

.difficulty-easy {
  background: #f3f4f6;
  color: #374151;
}

.difficulty-medium {
  background: #f3f4f6;
  color: #374151;
}

.difficulty-hard {
  background: #f3f4f6;
  color: #374151;
}

/* Collapsible Step Details */
.step-details {
  margin: 40px 0;
  border: 1px solid var(--border-color);
  border-radius: 16px;
  overflow: hidden;
  box-shadow: var(--shadow-sm);
}

.step-details-header {
  background: linear-gradient(135deg, #6b7280 0%, #9ca3af 100%);
  color: white;
  padding: 20px 24px;
  cursor: pointer;
  user-select: none;
  display: flex;
  align-items: center;
  justify-content: space-between;
  transition: all 0.2s ease;
}

.step-details-header:hover {
  background: linear-gradient(135deg, #4b5563 0%, #6b7280 100%);
}

.step-details-title {
  display: flex;
  align-items: center;
  gap: 12px;
  font-size: 1.3em;
  font-weight: 600;
  margin: 0;
}

.step-details-icon {
  font-size: 1.2em;
}

.step-details-toggle {
  font-size: 1.2em;
  transition: transform 0.3s ease;
}

.step-details[open] .step-details-toggle {
  transform: rotate(180deg);
}

.step-content {
  padding: 32px;
  background: var(--bg-white);
}

/* Simplified Content Sections */
.content-section {
  margin: 32px 0;
}

.content-section h4 {
  color: var(--text-primary);
  font-size: 1.1em;
  font-weight: 600;
  margin: 0 0 12px 0;
  display: flex;
  align-items: center;
  gap: 8px;
}

.content-section-icon {
  color: #6b7280;
}

.content-section p {
  color: var(--text-secondary);
  line-height: 1.6;
  margin: 0 0 16px 0;
}

/* Example Boxes - Simplified */
.example-box {
  background: #f8fafc;
  border: 1px solid var(--border-color);
  border-left: 4px solid var(--primary-color);
  border-radius: 8px;
  margin: 20px 0;
  overflow: hidden;
}

.example-header {
  background: var(--bg-white);
  padding: 16px 20px;
  border-bottom: 1px solid var(--border-color);
  cursor: pointer;
  user-select: none;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-weight: 600;
  color: #6b7280;
}

.example-content {
  padding: 20px;
  line-height: 1.6;
  color: var(--text-primary);
}

/* Content Sections - Restored Detail */
.content-section {
  margin: 24px 0;
}

.content-section h4 {
  color: var(--text-primary);
  font-size: 1.1em;
  font-weight: 600;
  margin: 0 0 12px 0;
  display: flex;
  align-items: center;
  gap: 8px;
}

.content-section-icon {
  color: #6b7280;
  font-size: 1.1em;
}

.content-section p {
  color: var(--text-secondary);
  line-height: 1.6;
  margin: 0 0 16px 0;
}

.content-section ul {
  margin: 12px 0;
  padding-left: 20px;
}

.content-section li {
  margin: 6px 0;
  color: var(--text-secondary);
  line-height: 1.5;
}

.content-section strong {
  color: var(--text-primary);
  font-weight: 600;
}

/* Responsive Design */
@media (max-width: 768px) {
  .template-header {
    padding: 32px 20px;
    margin: -20px -20px 24px -20px;
  }

  .template-title {
    font-size: 1.8em;
  }

  .template-features {
    flex-direction: column;
    align-items: center;
    gap: 12px;
  }

  .steps-grid {
    grid-template-columns: 1fr;
  }

  .quick-start-steps {
    grid-template-columns: 1fr;
    gap: 12px;
  }

  .beginner-guide {
    padding: 24px 20px;
    margin: 24px -20px;
  }

  .beginner-highlights {
    gap: 16px;
  }

  .highlight-item {
    flex-direction: column;
    gap: 12px;
    padding: 16px;
  }

  .highlight-icon {
    width: 36px;
    height: 36px;
    font-size: 1.3em;
  }

  .beginner-resources {
    padding: 20px;
  }

  .resource-grid {
    grid-template-columns: 1fr;
    gap: 16px;
  }

  .steps-intro {
    padding: 24px 20px;
    margin: 24px -20px;
  }

  .steps-intro h2 {
    font-size: 1.5em;
  }

  .steps-intro p {
    font-size: 1em;
  }
}

/* Smooth scrolling */
html {
  scroll-behavior: smooth;
}

/* Focus states for accessibility */
.step-card:focus,
.step-details-header:focus,
.example-header:focus {
  outline: 2px solid #6b7280;
  outline-offset: 2px;
}
</style>

<div class="beginner-guide">
  <div class="beginner-header">
    <h3 class="beginner-title">🚀 How to Use This Guide</h3>
  </div>
  <div class="beginner-content">
    <p><strong>Hey there!</strong> This guide walks you through building federated analytics projects from start to finish. Each step builds on the previous one, but feel free to adapt things to fit your specific needs and constraints.</p>

    <div class="beginner-highlights">
      <div class="highlight-item">
        <div class="highlight-icon">📖</div>
        <div class="highlight-content">
          <strong>Built on solid foundations</strong>
          <p>This guide builds on our <a href="/fl_life_cycle">FL Lifecycle</a> framework and pulls in lessons from real-world <a href="/fl_use_cases">FL Use Cases</a> across healthcare and research domains. <em>Want the academic background? Check out <a href="https://arxiv.org/abs/1912.04977">McMahan et al. (2021)</a> and <a href="https://www.sciencedirect.com/science/article/pii/S0950705121000381?casa_token=EnIpY-RiBh0AAAAA:zVcsrdkU-6ZSlNnnu99IuRcM75ZzysYEWi60iLupHEgRp-SDl5d6X2nZB7Vpej7MQZkPpvm7o8Q">Zhang et al. (2021)</a>.</em></p>
        </div>
      </div>

        <div class="highlight-item">
          <div class="highlight-icon">⚡</div>
          <div class="highlight-content">
            <strong>Practical focus</strong>
            <p>We'll build on solid theoretical foundations with actionable implementation steps. Each section includes real examples, common pitfalls, and specific deliverables you can implement right away. <em>Check out our <a href="/fl_use_cases">domain-specific examples</a>.</em></p>
          </div>
        </div>
    </div>

    <div class="beginner-resources">
      <h4>📚 Quick Start Paths</h4>
      <div class="resource-grid">
        <div class="resource-item">
          <strong>New to FL?</strong>
          <p>Start with our <a href="/fl_life_cycle">FL Lifecycle</a> and <a href="/fl_glossary">glossary</a>, then dive into <a href="/fl_use_cases">real examples</a>. <em>Want hands-on learning? Try our <a href="/all_training_resources">interactive tutorials</a>.</em></p>
        </div>
        <div class="resource-item">
          <strong>Ready to build?</strong>
          <p>Check out <a href="/fl_framework_assembly">framework selection</a> and browse our <a href="/all_tools_and_resources">tools & resources</a>. <em>Popular picks include <a href="https://flower.dev/">Flower</a>, <a href="https://github.com/OpenMined/PySyft">PySyft</a>, and <a href="https://www.tensorflow.org/federated">TensorFlow Federated</a>.</em></p>
        </div>
        <div class="resource-item">
          <strong>Need help?</strong>
          <p>Join our <a href="/community">community</a> or check out <a href="/all_training_resources">training materials</a>. <em>Looking for role-specific guidance? Check <a href="/your_role">our role pages</a>.</em></p>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="general-disclaimer">
  <p><strong>📋 Every Project is Unique:</strong> This guide gives you a solid roadmap for federated analytics implementation, but your journey will be shaped by your specific domain, data characteristics, and organizational context. Healthcare projects face different regulatory challenges than finance or research applications. <em>For regulatory guidance, check out <a href="https://gdpr-info.eu/">GDPR</a>, <a href="https://www.hhs.gov/hipaa">HIPAA</a>, and other relevant frameworks in your jurisdiction.</em></p>

  <p><strong>📅 Realistic Timelines:</strong> The timelines you'll see are based on successful projects across different domains. Your actual schedule will depend on data complexity, team experience, regulatory requirements, and infrastructure readiness. <em>Ethics approval alone can take months in many jurisdictions, so plan accordingly.</em> Use these estimates as planning references, not rigid deadlines.</p>

  <p><strong>🎯 Customize Your Approach:</strong> This guide covers the complete implementation pipeline, but you might need to adapt, skip, or modify steps based on your unique constraints. A research prototype has different requirements than a production healthcare system. <em>Check out our <a href="/fl_use_cases">use case library</a> for domain-specific examples and adaptations.</em> The goal is to give you a structured framework that you can tailor to your needs.</p>
</div>

<div class="steps-intro">
  <h2>🚀 Ready to Start? Here's Your Implementation Roadmap</h2>
  <p>Now that you know how to use this guide, let's dive into the four core steps that'll take you from initial concept to successful deployment. Each step builds on the previous one, with clear deliverables and checkpoints along the way.</p>
  <p><strong>💡 Pro tip:</strong> You can click on any step card below to jump straight to the detailed implementation guide, or scroll through them sequentially to get the complete picture.</p>
</div>

<div class="steps-overview">

  <div class="steps-grid">
    <div class="step-card step-card-1" onclick="document.querySelector('#planning').scrollIntoView({behavior: 'smooth'})">
      <div class="step-header">
        <div class="step-icon">01</div>
        <div class="step-info">
          <h2>🎯 Planning</h2>
          <div class="step-number">Step 1</div>
        </div>
      </div>
      <div class="step-description">
        Establish clear problem definition, regulatory compliance, and stakeholder alignment. This foundational step sets the stage for successful implementation by addressing governance, ethics, and strategic planning requirements.
      </div>
      <div class="step-key-points">
        <ul>
          <li>Problem definition and federation justification</li>
          <li>Ethics approval and legal compliance</li>
          <li>Stakeholder identification and team formation</li>
          <li>Project timeline and resource planning</li>
        </ul>
      </div>
      <div class="step-meta">
        <div class="step-meta-left">
          <div class="step-meta-item">
            <span class="step-meta-icon">⏱️</span>
            <span>1-6 months</span>
          </div>
          <div class="step-meta-item">
            <span class="step-meta-icon">👥</span>
            <span><a href="/your_role/principal_investigator" style="color: #7c3aed; text-decoration: none; font-weight: 500;">Principal Investigators</a>, <a href="/your_role/data_protection_officer" style="color: #7c3aed; text-decoration: none; font-weight: 500;">Legal Teams</a>, <a href="/your_role/coordinator" style="color: #7c3aed; text-decoration: none; font-weight: 500;">Ethics Coordinators</a></span>
          </div>
        </div>
        <div class="step-difficulty difficulty-easy">Foundation</div>
      </div>
    </div>

    <div class="step-card step-card-2" onclick="document.querySelector('#preparation').scrollIntoView({behavior: 'smooth'})">
      <div class="step-header">
        <div class="step-icon">02</div>
        <div class="step-info">
          <h2>🔧 Preparation</h2>
          <div class="step-number">Step 2</div>
        </div>
      </div>
      <div class="step-description">
        Characterize data sources, establish technical infrastructure, and implement preprocessing pipelines. This step transforms planning into actionable technical implementation with proper data harmonization and system architecture.
      </div>
      <div class="step-key-points">
        <ul>
          <li>Data exploration and quality assessment</li>
          <li>Infrastructure setup and security configuration</li>
          <li>Federation framework selection and testing</li>
          <li>Data preprocessing and standardization</li>
        </ul>
      </div>
      <div class="step-meta">
        <div class="step-meta-left">
          <div class="step-meta-item">
            <span class="step-meta-icon">⏱️</span>
            <span>2-12 weeks</span>
          </div>
          <div class="step-meta-item">
            <span class="step-meta-icon">👥</span>
            <span><a href="/your_role/data_steward" style="color: #7c3aed; text-decoration: none; font-weight: 500;">Data Teams</a>, <a href="/your_role/research_software_engineer" style="color: #7c3aed; text-decoration: none; font-weight: 500;">DevOps Engineers</a></span>
          </div>
        </div>
        <div class="step-difficulty difficulty-medium">Technical</div>
      </div>
    </div>

    <div class="step-card step-card-3" onclick="document.querySelector('#training').scrollIntoView({behavior: 'smooth'})">
      <div class="step-header">
        <div class="step-icon">03</div>
        <div class="step-info">
          <h2>⚙️ Training</h2>
          <div class="step-number">Step 3</div>
        </div>
      </div>
      <div class="step-description">
        Develop and implement federated algorithms, conduct model training, and establish privacy-preserving mechanisms. This step focuses on the core machine learning development with rigorous evaluation and security implementation.
      </div>
      <div class="step-key-points">
        <ul>
          <li>Algorithm design and model architecture</li>
          <li>Federated training implementation</li>
          <li>Privacy-preserving techniques (<a href ="https://link.springer.com/chapter/10.1007/11787006_1">differential privacy</a>, <a href ="https://www.researchgate.net/profile/Oded-Goldreich/publication/2934115_Secure_Multi-Party_Computation/links/00b7d52bb04f7027d4000000/Secure-Multi-Party-Computation.pdf">secure multi-party computation</a>)</li>
          <li>Performance evaluation and validation</li>
        </ul>
      </div>
      <div class="step-meta">
        <div class="step-meta-left">
          <div class="step-meta-item">
            <span class="step-meta-icon">⏱️</span>
            <span>Weeks-Months</span>
          </div>
          <div class="step-meta-item">
            <span class="step-meta-icon">👥</span>
            <span><a href="/your_role/federated_model_developer" style="color: #7c3aed; text-decoration: none; font-weight: 500;">Machine Learning Engineers</a>, <a href="/your_role/data_protection_officer" style="color: #7c3aed; text-decoration: none; font-weight: 500;">Security Teams</a></span>
          </div>
        </div>
        <div class="step-difficulty difficulty-hard">Research</div>
      </div>
    </div>

    <div class="step-card step-card-4" onclick="document.querySelector('#deployment').scrollIntoView({behavior: 'smooth'})">
      <div class="step-header">
        <div class="step-icon">04</div>
        <div class="step-info">
          <h2>🚀 Deployment</h2>
          <div class="step-number">Step 4</div>
        </div>
      </div>
      <div class="step-description">
        Ensure reproducibility, evaluate technology readiness, and facilitate knowledge transfer. This final step focuses on documentation, maturity assessment, and strategic planning for continued development or deployment.
      </div>
      <div class="step-key-points">
        <ul>
          <li>Reproducibility documentation and code sharing</li>
          <li>Model maturity assessment and validation</li>
          <li>Deployment planning and production readiness</li>
          <li>Results dissemination and knowledge transfer</li>
        </ul>
      </div>
      <div class="step-meta">
        <div class="step-meta-left">
          <div class="step-meta-item">
            <span class="step-meta-icon">⏱️</span>
            <span>2-8 weeks</span>
          </div>
          <div class="step-meta-item">
            <span class="step-meta-icon">👥</span>
            <span><a href="/your_role/researcher" style="color: #7c3aed; text-decoration: none; font-weight: 500;">Research Teams</a>, <a href="/your_role/principal_investigator" style="color: #7c3aed; text-decoration: none; font-weight: 500;">Leadership</a></span>
          </div>
        </div>
        <div class="step-difficulty difficulty-medium">Strategic</div>
      </div>
    </div>

  </div>
</div>

<div class="extended-version">
  <div class="extended-header">
    <strong>Need More Detail?</strong>
  </div>
  <p>This guide gives you a streamlined overview of the FL implementation process. Want more comprehensive guidance with detailed examples, checklists, and step-by-step instructions? Check out our <a href="#">Complete Template</a>.</p>
</div>

---

<details class="step-details" id="planning">
  <summary class="step-details-header">
    <div class="step-details-title">
      <span class="step-details-icon">🎯</span>
      <span>1. Planning</span>
    </div>
    <span class="step-details-toggle">▼</span>
  </summary>

  <div class="step-content">
    <div class="content-section">
      <h4><span class="content-section-icon">💡</span> What This Step Covers</h4>
      <p><strong>This is where everything begins.</strong> The planning step combines problem definition, scope setting, governance, and ethics approval. Before writing code or contacting potential partners, you need crystal-clear answers to fundamental questions: What problem are you solving? Why does it matter? Why cannot you just pool data centrally? What exactly will you deliver, and what is out of scope?</p>
      <p><strong>📚 New to federated learning?</strong> Start with our <a href="/fl_life_cycle">FL Lifecycle overview</a> and <a href="/fl_glossary">glossary</a> to understand key concepts. Explore <a href="/fl_use_cases">real-world use cases</a> to see how others have approached similar challenges.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">❓</span> Key Questions to Answer</h4>
      <p>What specific clinical, scientific, or operational gap are you filling? Who benefits (patients, researchers, policymakers)? Why is federated analytics necessary rather than just preferable? What does success look like concretely? What assumptions underpin your approach, and how will you validate them?</p>
      <p><strong>💡 Pro tip:</strong> Use our <a href="/fl_use_cases">FL Use Cases</a> to see how others have justified federation for similar problems.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">👥</span> Who Is Involved</h4>
      <p><strong><a href="/your_role/principal_investigator">Principal investigators</a> and domain experts</strong> define the problem and objectives. <strong><a href="/your_role/data_protection_officer">Legal and compliance officers</a></strong> identify regulatory barriers to centralization. <strong><a href="/your_role/coordinator">Ethics committees</a></strong> review protocols. <strong>Project managers</strong> establish scope boundaries and timelines. <strong>Funding agencies</strong> assess whether problem justifies resources.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">⏱️</span> Timeline</h4>
      <p><strong>Initial scoping:</strong> 1-2 weeks of stakeholder discussions and literature review. <strong>Ethics and governance:</strong> 3-6 months (often the longest step). <strong>Refinement happens throughout project</strong> as you learn more, but major scope changes after the next step are costly.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">⚠️</span> Common Mistakes</h4>
      <p>Vague problem statements ("improve healthcare"), unrealistic objectives (overpromising performance), weak federation justification (could actually centralize with proper agreements), underestimating ethics timeline, unclear authorship rules leading to publication conflicts.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">📦</span> Deliverables</h4>
      <p>One-page project summary, stakeholder list with commitments, signed consortium agreement or data use agreements, ethics approval letters with reference numbers, explicit list of in-scope and out-of-scope deliverables, documented assumptions with validation plan.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">📝</span> What to Document</h4>
      <ul>
        <li><strong>Problem and Domain:</strong> Describe the clinical, scientific, or operational challenge you are addressing in plain language. What gap in knowledge or capability are you filling? Who will benefit from solving this problem?</li>
        <li><strong>Why Federated Analytics:</strong> Explain the specific barriers preventing centralized data pooling. These might be regulatory (<a href="https://gdpr-info.eu/">GDPR</a>, <a href="https://www.hhs.gov/hipaa">HIPAA</a>), institutional policy, data ownership concerns, trust issues between organizations, technical infrastructure limitations, or competitive considerations.</li>
        <li><strong>Primary Objective:</strong> State your single most important goal in concrete, measurable terms. Be specific about what success looks like. Examples: "Train a prognostic model achieving AUROC ≥0.80" or "Estimate treatment effect heterogeneity across 20 sites with 95% confidence intervals."</li>
        <li><strong>Population and Setting:</strong> Describe your data subjects or sources. For clinical studies: patient populations, inclusion/exclusion criteria, geographic and temporal scope. For other domains: IoT devices, sensor networks, administrative databases, etc.</li>
        <li><strong>Stakeholders and Roles:</strong> List all key participants with their roles and responsibilities: principal investigators, data custodians at each site, technical developers, funders, oversight bodies, and end users.</li>
        <li><strong>Ethics and Approvals:</strong> Name all institutional review boards, ethics committees, or data protection impact assessments that reviewed and approved your work. Include approval reference numbers, dates, and key conditions or restrictions.</li>
        <li><strong>Legal Basis and Agreements:</strong> Describe the legal foundation for data processing (GDPR Article citations, HIPAA provisions, institutional policies). List data use agreements, consortium contracts, or memoranda of understanding between participating organizations.</li>
        <li><strong>Access and Sharing Policy:</strong> Specify who can access what. For raw data: controlled access procedures, credentialing requirements. For intermediate artifacts: sharing rules. For results: publication policies, embargoes, site-level result disclosure rules.</li>
        <li><strong>Outputs:</strong> List all deliverables. For modeling projects: trained models, performance metrics, calibration curves. For analytics: summary statistics, dashboards, reports. For infrastructure: frameworks, APIs, deployment guides.</li>
        <li><strong>Out of Scope:</strong> Explicitly state what this project will NOT address. This prevents misunderstandings and helps focus resources.</li>
        <li><strong>Assumptions and Constraints:</strong> List key assumptions underlying your approach (e.g., "Sites use consistent diagnostic criteria," "Clients remain online during training"). Note technical, organizational, and regulatory constraints. Describe how you will validate assumptions.</li>
      </ul>
    </div>

    <div class="example-box">
      <div class="example-header">
        <span>📝 Example: <a href="https://journals.plos.org/digitalhealth/article?id=10.1371/journal.pdig.0000533">FL-MS Study Planning</a></span>
      </div>
      <div class="example-content">
        <p><strong>Background:</strong> This example is based on a real-world federated learning study for multiple sclerosis (MS) disability progression prediction, published in <a href="#Pirmani2025-sd">Pirmani et al. (2025)</a>. The study demonstrates how federated learning can be applied to clinical prediction tasks while maintaining data privacy and regulatory compliance.</p>

        <p><strong>Problem:</strong> Early prediction of disability progression in multiple sclerosis (MS) remains challenging despite its critical importance for therapeutic decision-making. MS affects millions of people worldwide <a href="https://journals.sagepub.com/doi/full/10.1177/1352458520970841">(Walton et al., 2020)</a>, with each patient experiencing unique disease progressions and varying responses to treatment. The primary challenge lies in capturing this heterogeneity to enable personalized, data-driven treatment strategies. While <a href="https://journals.plos.org/digitalhealth/article?id=10.1371/journal.pdig.0000533">machine learning shows promise</a> for improving our understanding of MS progression and predicting individual treatment responses, developing advanced ML models remains constrained by limited access to large-scale, high-quality datasets. Although MS impacts an estimated 2.8 million individuals globally, clinical data needed for precision modeling remain <a href="https://journals.sagepub.com/doi/full/10.1177/1352458520941485">fragmented and siloed across healthcare institutions</a>.</p>

        <p><strong>Why Federated:</strong> Aggregating MS clinical data across international institutions is complicated by legitimate but complex regulatory constraints (<a href="https://gdpr-info.eu/">GDPR</a>, national health data laws), data ownership concerns, and inconsistent data quality standards. <a href="https://medinform.jmir.org/2023/1/e48030/">Healthcare institutions are reluctant to share raw patient records</a> due to privacy regulations, competitive concerns, and liability fears. Federated learning offers a decentralized learning paradigm that enables training ML models while preserving data localization, strongly aligned with data privacy and protection standards. This approach allows <a href="https://formative.jmir.org/2024/1/e55496">collaborative model development</a> without requiring data centralization.</p>

        <p><strong>Objective:</strong> Assess whether <a href="https://arxiv.org/abs/2103.00710">personalized federated learning</a> can match or exceed centralized model performance in predicting 2-year disability progression in multiple sclerosis patients, while maintaining data localization and privacy. Success defined as achieving comparable ROC-AUC to centralized baseline (~0.81) using federated approaches across multiple international sites.</p>

        <p><strong>Ethics Approval:</strong> Hasselt University and KU Leuven PRET Approval: G 2023 6771. Legal Basis: <a href="https://gdpr-info.eu/art-6-gdpr/">GDPR Article 6(1)(e)</a> + <a href="https://gdpr-info.eu/art-9-gdpr/">Article 9(2)(j)</a> for health data research with appropriate safeguards.</p>
      </div>
    </div>

  </div>
</details>

<details class="step-details" id="preparation">
  <summary class="step-details-header">
    <div class="step-details-title">
      <span class="step-details-icon">🔧</span>
      <span>2. Preparation</span>
    </div>
    <span class="step-details-toggle">▼</span>
  </summary>

  <div class="step-content">
    <div class="content-section">
      <h4><span class="content-section-icon">💡</span> What This Step Covers</h4>
      <p><strong>This is where planning becomes implementation.</strong> The preparation step combines data understanding, infrastructure setup, and technical architecture. You will characterize what data exist at each site, understand data heterogeneity, set up federation infrastructure, and prepare data pipelines for federated training.</p>
      <p><strong>🛠️ Need framework guidance?</strong> Check our <a href="/fl_framework_assembly">FL Framework Assembly</a> and <a href="/all_tools_and_resources">Tools and Resources</a> for technical recommendations. For data harmonization challenges, explore our <a href="/fl_use_cases">use case examples</a>.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">❓</span> Key Questions to Answer</h4>
      <p>Where does your data live? How many clients will participate? How different are they from each other (data volume, feature distributions, outcome prevalence)? What clinical or technical vocabularies do you need to align? What data quality issues exist? How will you handle train/test splits in distributed setting? What normalization strategy avoids information leakage?</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">👥</span> Who Is Involved</h4>
      <p><strong><a href="/your_role/data_steward">Data engineers</a> at each site</strong> implement local preprocessing pipelines. <strong><a href="/your_role/federated_model_developer">Machine learning engineers</a></strong> set up federation framework (Flower, PySyft, TensorFlow Federated, etc.). <strong>IT administrators</strong> configure servers and network access. <strong><a href="/your_role/research_software_engineer">DevOps engineers</a></strong> handle monitoring and logging. <strong>System architects</strong> design topology.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">⏱️</span> Timeline</h4>
      <p><strong>Data characterization:</strong> 2-4 weeks. <strong>Infrastructure setup:</strong> 2-4 weeks. <strong>Integration and debugging:</strong> 2-4 weeks. <strong>Total:</strong> 4-12 weeks depending on number of sites and technical complexity. More sites equals more coordination overhead.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">⚠️</span> Common Mistakes</h4>
      <p>Assuming all sites have similar data quality or feature availability, underestimating harmonization effort, ignoring extreme heterogeneity that might make federation infeasible, inconsistent preprocessing across sites (subtle bugs multiply), ignoring data leakage (test statistics leaking into normalization), underestimating infrastructure complexity (firewalls, authentication, monitoring).</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">📦</span> Deliverables</h4>
      <p>Client inventory with data volumes, data quality assessment reports from each site, harmonization mapping documents, validated preprocessing pipelines running at each site, federation infrastructure passing integration tests, monitoring dashboards operational, documented hardware and software specifications, runbooks for troubleshooting common issues.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">📝</span> What to Document</h4>
      <ul>
        <li><strong>Data Sources:</strong> List all participating data silos (hospitals, clinics, research cohorts, IoT deployments). Provide context on their systems: EHR vendors, data collection protocols, approximate data volumes. Describe how you defined "clients" (by institution, by country, by device type, etc.).</li>
        <li><strong>Federation Mode:</strong> Specify whether you are using simulated federation (single infrastructure with partitioned data), live federation (truly distributed clients), or hybrid approaches. If simulated: describe data partitioning strategy and what real-world factors you are NOT capturing.</li>
        <li><strong>Inclusion Criteria:</strong> Define eligibility for records, subjects, or data samples at both the dataset level (which sites participate) and record level (which observations are analyzed). Document any temporal restrictions, data quality filters, or minimum sample size requirements.</li>
        <li><strong>Features and Data Dictionary:</strong> List all variables used in your analysis, grouped by type (demographics, clinical measures, lab values, etc.). Provide or link to a detailed data dictionary with units, permissible ranges, and definitions. Note any derived features (feature engineering).</li>
        <li><strong>Outcome Definitions:</strong> For supervised learning: precisely define your target variable(s). For hypothesis testing: state your null and alternative hypotheses. Include operational definitions, time windows, confirmation requirements, and any exclusions.</li>
        <li><strong>Dataset Characteristics:</strong> Report sample sizes (total and per client), class balance or outcome prevalence, known biases or selection effects, and missing data patterns. Quantify heterogeneity across clients if applicable.</li>
        <li><strong>Data Quality and Harmonization:</strong> Note any data quality issues discovered during exploration (missingness, outliers, measurement errors). List vocabularies, ontologies, coding systems, and unit conventions used for harmonization across sites.</li>
        <li><strong>Local Data Preparation:</strong> Describe your complete preprocessing pipeline: data transformations, filtering, feature engineering, temporal windowing, and quality checks. Explain how you create train/validation/test splits (temporal, random, stratified). Detail your normalization strategy (local statistics, global statistics, fixed references).</li>
        <li><strong>Federation Infrastructure:</strong> Describe your network topology (star, hierarchical, peer-to-peer), orchestration framework, scheduling approach, client participation policies, and hardware specifications. Include monitoring, failure recovery, and baseline security measures (transport encryption, authentication).</li>
      </ul>
    </div>

    <div class="example-box">
      <div class="example-header">
        <span>📝 Example: FL-MS Study Preparation</span>
      </div>
      <div class="example-content">
        <p><strong>Data Source:</strong><a href="https://doi.org/10.1177/1352458506070775"> MSBase international</a> MS registry, a large prospective observational cohort collecting routine clinical data from MS patients worldwide. Clients defined at country level, resulting in multiple federated sites. This choice balances sufficient sample size per client (many countries have 1000+ patients) with meaningful clinical heterogeneity (MS care practices, genetic backgrounds, environmental factors vary by country).</p>

        <p><strong>Federation Mode:</strong> Simulated on Flanders Supercomputer, captures data heterogeneity but not real network challenges. Data partitioned by country to create multiple virtual clients, but all data physically reside on same computing cluster. Each virtual client has exclusive access to its country's data subset during training (enforced programmatically).</p>

        <p><strong>Features:</strong> 42 tabular features including demographics, Expanded Disability Status Scale (EDSS) scores, relapse history, treatment records. Outcome: Confirmed Disability Progression (CDP), sustained EDSS increase confirmed at 6 months. Final dataset: 283,115 episodes from 26,246 patients across multiple countries.</p>

        <p><strong>Infrastructure:</strong> Centralized star topology with Flower 1.5.0, 32 clients on Flanders Supercomputer. Preprocessing: Episode construction with 3.25-year observation windows, 60/20/20 train/validation/test splits at patient level. Normalization: Per-client using training set statistics to avoid information leakage.</p>
      </div>
    </div>

  </div>
</details>

<details class="step-details" id="training">
  <summary class="step-details-header">
    <div class="step-details-title">
      <span class="step-details-icon">⚙️</span>
      <span>3. Training</span>
    </div>
    <span class="step-details-toggle">▼</span>
  </summary>

  <div class="step-content">
    <div class="content-section">
      <h4><span class="content-section-icon">💡</span> What This Step Covers</h4>
      <p><strong>This is where the federated learning happens.</strong> The training step combines algorithm development, model training, evaluation, and privacy/security implementation. You will design your analytical approach, train models, rigorously evaluate results, and implement technical safeguards. This step generates your scientific findings and determines whether federated analytics successfully solved your problem.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">❓</span> Key Questions to Answer</h4>
      <p>What algorithms will you test? How do they handle data heterogeneity across clients? What does "success" look like (metrics, thresholds)? How does federated performance compare to centralized and local-only baselines? Does the model work fairly across all participating sites? What could go wrong (threat model)? What defenses have you implemented?</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">👥</span> Who Is Involved</h4>
      <p><strong><a href="/your_role/federated_model_developer">Data scientists and machine learning engineers</a></strong> design and implement methods. <strong>Domain experts</strong> (clinicians, scientists) validate that approach makes sense for the problem. <strong>Statisticians</strong> ensure rigorous evaluation. <strong><a href="/your_role/data_protection_officer">Security engineers</a></strong> conduct threat modeling and implement controls. <strong>Privacy experts</strong> assess re-identification risks. <strong>Site coordinators</strong> support distributed execution.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">⏱️</span> Timeline</h4>
      <p><strong>Algorithm development:</strong> Weeks to months depending on complexity. <strong>Training and evaluation:</strong> Weeks to months depending on number of experiments and computational resources. <strong>Privacy/security implementation:</strong> 2-8 weeks for basic controls, 4-8+ weeks for advanced privacy tech (<a href="https://en.wikipedia.org/wiki/Differential_privacy">differential privacy</a>, <a href="https://en.wikipedia.org/wiki/Secure_multi-party_computation">secure multi-party computation</a>). <strong>Total:</strong> This is typically the longest step.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">⚠️</span> Common Mistakes</h4>
      <p>Assuming "federated equals private" automatically (not true without additional safeguards), ignoring simulation versus production threat model differences, implementing differential privacy without understanding epsilon parameters, over-claiming privacy guarantees, no incident response plan, not including centralized baseline to quantify privacy-utility trade-off.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">📦</span> Deliverables</h4>
      <p>Trained models or computed statistics, comprehensive performance reports comparing multiple approaches, fairness analysis showing per-client results, documented hyperparameters and training configurations, threat model document, implemented security controls checklist, privacy impact assessment, incident response plan.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">📝</span> What to Document</h4>
      <ul>
        <li><strong>Algorithm Selection:</strong> List all algorithms tested, both federated (FedAvg, FedProx, etc.) and baselines (centralized, local-only). Describe your model architecture in detail. Explain hyperparameter choices and how you tuned them. Document training schedules (number of rounds, local epochs, batch sizes, early stopping).</li>
        <li><strong>Evaluation and Success Criteria:</strong> Define your primary metric (the ONE number you will use to judge success) and secondary metrics. Explain how evaluation happens: where are models tested (centrally or at each client), how do you aggregate local performance metrics, and how do you ensure test data never leaked into training. Compare federated performance to three baselines: (1) centralized, (2) local-only, (3) simpler methods.</li>
        <li><strong>Fairness Analysis:</strong> Do results hold across all clients, or do some sites get worse predictions? Report performance stratified by client size, class balance, or other relevant factors.</li>
        <li><strong>Threat Model and Controls:</strong> Identify potential adversaries (honest-but-curious server, malicious clients, external attackers, insiders) and attack vectors (model inversion, membership inference, gradient leakage, Byzantine updates). List implemented defenses (secure aggregation, encryption, differential privacy, access logging).</li>
        <li><strong>Privacy Guarantees:</strong> What protection is actually provided? If using differential privacy: document privacy budget accounting. For simulations: note how threat model differs from live deployment. Be transparent about what is and is not protected.</li>
        <li><strong>Reproducibility:</strong> Set and document random seeds for reproducibility. Note any sources of non-determinism (GPU operations, asynchronous updates, client ordering effects). Document software versions, hardware specs, dependencies.</li>
      </ul>
    </div>

    <div class="example-box">
      <div class="example-header">
        <span>📝 Example: FL-MS Study Training</span>
      </div>
      <div class="example-content">
        <p><strong>Architecture:</strong> 5-layer Multi-Layer Perceptron (MLP) (512 neurons/layer) with AdaptiveDualBranchNet for personalization. Total parameters: ~330K. Centralized baseline achieved ROC-AUC ~0.81, PR-AUC ~0.46 on country-partitioned test set.</p>

        <p><strong>Key Finding:</strong> Personalized FL achieved ROC-AUC 0.84 ± 0.002, exceeding centralized baseline (0.81). Small clients benefit most from personalization, large clients show modest gains. 10 repeated runs with different seeds, low variance across experiments (SD ~0.001-0.003).</p>

        <p><strong>Threat Model:</strong> Honest-but-curious server attempting to infer patient information from model updates. Controls: Data localization, aggregation-based privacy, no raw data sharing, access controls. Limitations: No differential privacy (would degrade performance), no secure multi-party computation (complexity versus benefit).</p>

        <p><strong>Reproducibility:</strong> Seeds 0-9 for 10 runs, highly reproducible results. Environment: Python 3.9, PyTorch 1.12.1, Flower 1.5.0 on Linux with Intel Xeon CPUs.</p>
      </div>
    </div>

  </div>
</details>

<details class="step-details" id="deployment">
  <summary class="step-details-header">
    <div class="step-details-title">
      <span class="step-details-icon">🚀</span>
      <span>4. Deployment</span>
    </div>
    <span class="step-details-toggle">▼</span>
  </summary>

  <div class="step-content">
    <div class="content-section">
      <h4><span class="content-section-icon">💡</span> What This Step Covers</h4>
      <p><strong>This step honestly assesses where you are and what comes next.</strong> The deployment step combines reproducibility, sharing, and maturity assessment. Making your work reproducible is not optional, it is a scientific and ethical obligation. This step documents everything someone else needs to validate your findings or apply your methods to their own data. Not every federated learning project needs to reach production deployment, many generate valuable scientific insights while remaining research tools.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">❓</span> Key Questions to Answer</h4>
      <p>Can someone else reproduce your results with access to the same (or similar) data? Have you documented enough detail about your environment, hyperparameters, and preprocessing that results should be identical? Is this production-ready, or proof-of-concept? What evidence supports your maturity claim? What would it actually take (time, money, people, approvals) to reach the next level?</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">👥</span> Who Is Involved</h4>
      <p><strong><a href="/your_role/research_software_engineer">Research software engineers</a></strong> ensure code quality and documentation. <strong><a href="/your_role/data_steward">Data stewards</a></strong> document data access procedures. <strong><a href="/your_role/data_protection_officer">Legal/ethics teams</a></strong> review what can be publicly shared. <strong><a href="/your_role/principal_investigator">Principal investigators</a></strong> assess scientific maturity. <strong>Clinical champions</strong> evaluate deployment feasibility. <strong>IT leaders</strong> estimate infrastructure requirements. <strong>Funders</strong> consider return on investment.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">⏱️</span> Timeline</h4>
      <p><strong>Reproducibility documentation:</strong> 2-4 weeks for code cleanup, documentation writing, and artifact archiving. <strong>Technology Readiness Level (TRL) assessment:</strong> 1-2 weeks after results finalize. <strong>Gap analysis and roadmap:</strong> 1-2 weeks if pursuing deployment. <strong>Total:</strong> 2-8 weeks depending on scope of sharing and deployment plans.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">⚠️</span> Common Mistakes</h4>
      <p>Waiting until submission deadline to organize code (leads to rushed, poor documentation), forgetting to document version numbers, releasing code that cannot run without undocumented dependencies, not explaining data access process clearly, overstating maturity (damages credibility), understating maturity (misses deployment opportunities).</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">📦</span> Deliverables</h4>
      <p>Public code repository with documentation, environment specification files, archived artifacts with persistent identifiers (DOIs), data access guide, documented limitations, TRL assessment with evidence, gap analysis with resource estimates, deployment roadmap OR research-only justification, lessons learned document, recommendations for future work.</p>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">📝</span> What to Document</h4>
      <ul>
        <li><strong>Code Repository:</strong> GitHub/GitLab repository URL with specific commit hash or release tag used for published results. README explaining how to run code. Requirements file with package versions. If using containers: Docker image tags or Conda environment files.</li>
        <li><strong>Environment:</strong> Software versions (Python, R, libraries), operating system, hardware (CPU/GPU specs). Note: exact hardware may not be reproducible, but document what you used.</li>
        <li><strong>Random Seeds:</strong> All seeds for data splits, initialization, sampling. Mention sources of non-determinism (GPU operations, async updates).</li>
        <li><strong>Data Availability:</strong> Choose one path and explain clearly: (1) Public - provide dataset name and download link, (2) Restricted - explain application process, timeline, costs, (3) Synthetic - provide generator scripts or synthetic samples.</li>
        <li><strong>Artifacts:</strong> List everything you are releasing: model weights (if allowed by governance), configuration files, evaluation outputs, figures. Use persistent identifiers (Zenodo DOI, Figshare).</li>
        <li><strong>Limitations:</strong> Be honest about what does not work, what you could not validate, and where your approach might not generalize.</li>
        <li><strong>TRL Assessment:</strong> Claim specific TRL (or range like 4-5) and justify with evidence: publications, pilot results, user feedback, regulatory interactions, deployment case studies.</li>
        <li><strong>Gap Analysis:</strong> For each gap to next TRL, specify: (1) What needs to happen, (2) Who needs to do it, (3) Estimated time and cost, (4) Key risks or blockers.</li>
        <li><strong>Lessons Learned:</strong> What worked well that you would recommend to others? What surprised you or turned out harder than expected? What would you do differently if starting over? What assumptions that turned out wrong?</li>
        <li><strong>Next Steps:</strong> If continuing the work: prioritized action items with timelines and resource estimates. If wrapping up: suggestions for what future research should tackle.</li>
      </ul>
    </div>

    <div class="content-section">
      <h4><span class="content-section-icon">📊</span> Technology Readiness Levels</h4>
      <ul>
        <li><strong>TRL 1-3:</strong> Basic research, proof of concept on toy data</li>
        <li><strong>TRL 4:</strong> Technology validated in lab (realistic data, controlled environment)</li>
        <li><strong>TRL 5:</strong> Technology validated in relevant environment (simulation with real data characteristics)</li>
        <li><strong>TRL 6:</strong> Technology demonstrated in relevant environment (pilot with actual users)</li>
        <li><strong>TRL 7-8:</strong> System prototype demonstration in operational environment</li>
        <li><strong>TRL 9:</strong> Actual system proven in operational use</li>
      </ul>
    </div>

    <div class="example-box">
      <div class="example-header">
        <span>📝 Example: FL-MS Study Deployment</span>
      </div>
      <div class="example-content">
        <p><strong>Code:</strong> GitHub repository with Apache 2.0 license, includes preprocessing, training, and evaluation scripts. Environment: Python 3.9, PyTorch 1.12.1, Flower 1.5.0 on Linux with Intel Xeon CPUs. Reproducibility: Seeds 0-9 for 10 runs, highly reproducible results (SD ~0.001-0.003).</p>

        <p><strong>Data Access:</strong> Restricted - researchers can apply at www.msbase.org with 2-6 month approval timeline. Model weights: NOT released (privacy concerns even for aggregated models, plus MSBase data use restrictions).</p>

        <p><strong>Current TRL:</strong> 4-5 (validated in simulation with realistic data, published in peer-reviewed journal). Gaps to TRL 6-7: Live federation deployment, prospective validation, clinical usability studies, regulatory pathway. Timeline to TRL 7: 2-3 years</p>

        <p><strong>Key Lessons:</strong> Personalization crucial for heterogeneous data, simulation valuable for algorithm development, stakeholder engagement needed earlier. Next steps: Apply for funding for live deployment pilot, identify 3-5 MSBase sites willing to pilot live FL infrastructure.</p>
      </div>
    </div>

  </div>
</details>

<script>
// Simple smooth scrolling for anchor links
document.addEventListener('DOMContentLoaded', function() {
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
      e.preventDefault();
      const target = document.querySelector(this.getAttribute('href'));
      if (target) {
        target.scrollIntoView({ behavior: 'smooth' });
      }
    });
  });
});
</script>
