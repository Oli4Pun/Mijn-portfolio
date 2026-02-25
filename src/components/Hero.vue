<template>
  <section class="hero">
    <div class="hero-content">
      <div class="hero-label">{{ label }}</div>
      <h1 class="hero-title">
        <span class="hero-name">{{ name }}</span>
        <span class="hero-tagline">{{ tagline }}</span>
      </h1>
      <p class="hero-description">{{ description }}</p>
      <div class="hero-cta">
        <a href="#contact" class="btn btn-primary" @click.prevent="scrollToSection('#contact')">
          Get in touch
        </a>
        <a href="#work" class="btn btn-secondary" @click.prevent="scrollToSection('#work')">
          View my work
        </a>
      </div>
    </div>
    <div class="hero-accent"></div>
  </section>
</template>

<script>
export default {
  name: 'Hero',
  data() {
    return {
      label: 'Junior Developer & IT Support',
      name: 'Olivier Punie',
      tagline: 'Building digital experiences',
      description: 'Gemotiveerde IT-professional met een graduaat in programmeren. Sterk in softwareontwikkeling en data-analyse, met oog voor detail en een probleemoplossende aanpak.'
    }
  },
  methods: {
    scrollToSection(href) {
      const element = document.querySelector(href)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth', block: 'start' })
      }
    }
  }
}
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  padding: var(--spacing-xl) var(--spacing-md);
  overflow: hidden;
}

.hero-content {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  z-index: 2;
}

.hero-label {
  font-family: var(--font-mono);
  font-size: 0.85rem;
  color: var(--color-accent);
  letter-spacing: 0.1em;
  text-transform: uppercase;
  margin-bottom: var(--spacing-sm);
  animation: fadeInUp 0.6s ease 0.2s both;
}

.hero-title {
  font-family: var(--font-display);
  font-weight: 700;
  margin-bottom: var(--spacing-md);
}

.hero-name {
  display: block;
  font-size: clamp(2.5rem, 8vw, 5rem);
  line-height: 1.1;
  background: linear-gradient(135deg, var(--color-gradient-start), var(--color-gradient-end));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: fadeInUp 0.6s ease 0.4s both;
}

.hero-tagline {
  display: block;
  font-size: clamp(1.5rem, 4vw, 2.5rem);
  font-weight: 300;
  color: var(--color-text-muted);
  margin-top: var(--spacing-xs);
  animation: fadeInUp 0.6s ease 0.6s both;
}

.hero-description {
  max-width: 600px;
  font-size: 1.1rem;
  color: var(--color-text-muted);
  line-height: 1.8;
  margin-bottom: var(--spacing-md);
  animation: fadeInUp 0.6s ease 0.8s both;
}

.hero-cta {
  display: flex;
  gap: var(--spacing-sm);
  flex-wrap: wrap;
  animation: fadeInUp 0.6s ease 1s both;
}

.hero-accent {
  position: absolute;
  top: -10%;
  right: -20%;
  width: 80%;
  height: 120%;
  background: linear-gradient(135deg, rgba(79, 70, 229, 0.05), rgba(6, 182, 212, 0.05));
  transform: rotate(15deg);
  z-index: 1;
  animation: slideInRight 1s ease;
}

.btn {
  display: inline-block;
  padding: 0.875rem 2rem;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.95rem;
  border-radius: 6px;
  transition: all var(--transition-normal);
  border: 2px solid transparent;
}

.btn-primary {
  background: var(--color-accent);
  color: white;
}

.btn-primary:hover {
  background: var(--color-accent-light);
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(255, 107, 53, 0.3);
}

.btn-secondary {
  background: transparent;
  color: var(--color-text);
  border-color: var(--color-border);
}

.btn-secondary:hover {
  border-color: var(--color-accent);
  color: var(--color-accent);
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .hero {
    padding: var(--spacing-lg) var(--spacing-sm);
  }
  
  .hero-cta {
    flex-direction: column;
  }
  
  .btn {
    text-align: center;
  }
}
</style>