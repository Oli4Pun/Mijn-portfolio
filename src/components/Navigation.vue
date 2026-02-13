<template>
  <nav class="nav">
    <div class="nav-container">
      <div class="nav-logo">OP</div>
      <ul class="nav-menu">
        <li v-for="link in navLinks" :key="link.href">
          <a 
            :href="link.href" 
            class="nav-link"
            @click.prevent="scrollToSection(link.href)"
          >
            {{ link.text }}
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navigation',
  data() {
    return {
      navLinks: [
        { href: '#about', text: 'About' },
        { href: '#work', text: 'Work' },
        { href: '#skills', text: 'Skills' },
        { href: '#contact', text: 'Contact' }
      ]
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
.nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  z-index: 1000;
  border-bottom: 1px solid var(--color-border);
  animation: slideDown 0.5s ease;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: var(--spacing-sm) var(--spacing-md);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-logo {
  font-family: var(--font-mono);
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--color-primary);
  letter-spacing: -0.05em;
}

.nav-menu {
  display: flex;
  list-style: none;
  gap: var(--spacing-md);
}

.nav-link {
  text-decoration: none;
  color: var(--color-text);
  font-weight: 500;
  font-size: 0.95rem;
  position: relative;
  transition: color var(--transition-fast);
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--color-accent);
  transition: width var(--transition-normal);
}

.nav-link:hover {
  color: var(--color-accent);
}

.nav-link:hover::after {
  width: 100%;
}

@media (max-width: 768px) {
  .nav-menu {
    gap: var(--spacing-sm);
  }
}

@media (max-width: 480px) {
  .nav-logo {
    font-size: 1.25rem;
  }
  
  .nav-menu {
    gap: 0.75rem;
  }
  
  .nav-link {
    font-size: 0.85rem;
  }
}
</style>