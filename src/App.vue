<template>
  <div id="app">
    <Navigation />
    <Hero />
    <About />
    <Experience />
    <Skills />
    <Contact />
    <Footer />
  </div>
</template>

<script>
import Navigation from './components/Navigation.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Experience from './components/Experience.vue'
import Skills from './components/Skills.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Navigation,
    Hero,
    About,
    Experience,
    Skills,
    Contact,
    Footer
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Archivo:wght@300;400;600;700&family=JetBrains+Mono:wght@400;500&display=swap');

:root {
  --color-primary: #0A0E27;
  --color-accent: #FF6B35;
  --color-accent-light: #FF8C61;
  --color-text: #1A1A2E;
  --color-text-muted: #4A5568;
  --color-bg: #FAFAFA;
  --color-surface: #FFFFFF;
  --color-border: #E2E8F0;
  --color-gradient-start: #4F46E5;
  --color-gradient-end: #06B6D4;
  
  --font-display: 'Archivo', sans-serif;
  --font-body: 'Archivo', sans-serif;
  --font-mono: 'JetBrains Mono', monospace;
  
  --spacing-xs: 0.5rem;
  --spacing-sm: 1rem;
  --spacing-md: 2rem;
  --spacing-lg: 4rem;
  --spacing-xl: 6rem;
  
  --transition-fast: 0.2s ease;
  --transition-normal: 0.3s ease;
  --transition-slow: 0.5s ease;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: var(--font-body);
  color: var(--color-text);
  background-color: var(--color-bg);
  line-height: 1.6;
  font-size: 16px;
  overflow-x: hidden;
}

#app {
  width: 100%;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--spacing-md);
}

.section {
  padding: var(--spacing-xl) 0;
}

.section-header {
  display: flex;
  align-items: center;
  gap: var(--spacing-md);
  margin-bottom: var(--spacing-lg);
}

.section-number {
  font-family: var(--font-mono);
  font-size: 1rem;
  color: var(--color-accent);
  font-weight: 600;
}

.section-title {
  font-family: var(--font-display);
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 700;
  color: var(--color-primary);
}

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

@keyframes slideDown {
  from {
    transform: translateY(-100%);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

@keyframes slideInRight {
  from {
    transform: translateX(100%) rotate(15deg);
    opacity: 0;
  }
  to {
    transform: translateX(0) rotate(15deg);
    opacity: 1;
  }
}

@media (max-width: 768px) {
  .section {
    padding: var(--spacing-lg) 0;
  }
  
  .section-header {
    flex-direction: column;
    align-items: flex-start;
    gap: var(--spacing-xs);
  }
}
</style>