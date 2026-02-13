<template>
  <section id="contact" class="section contact">
    <div class="container">
      <div class="section-header">
        <span class="section-number">04</span>
        <h2 class="section-title">Let's Connect</h2>
      </div>
      <div class="contact-content">
        <div class="contact-info">
          <p class="contact-lead">{{ leadText }}</p>
          <div class="contact-methods">
            <a 
              v-for="method in contactMethods" 
              :key="method.text"
              :href="method.href" 
              class="contact-method"
              :class="{ 'not-link': !method.href }"
            >
              <span class="contact-icon">{{ method.icon }}</span>
              <span class="contact-text">{{ method.text }}</span>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      leadText: 'Interested in working together or have a question? Feel free to reach out!',
      contactMethods: [
        {
          icon: '✉',
          text: 'olivier11181.punie@gmail.com',
          href: 'mailto:olivier11181.punie@gmail.com'
        },
        {
          icon: '☎',
          text: '+32 471 93 75 42',
          href: 'tel:+32471937542'
        },
        {
          icon: '📍',
          text: '3740 Bilzen, Belgium',
          href: null
        }
      ]
    }
  }
}
</script>

<style scoped>
.contact {
  background: var(--color-surface);
}

.contact-content {
  max-width: 800px;
}

.contact-lead {
  font-size: 1.25rem;
  color: var(--color-text);
  margin-bottom: var(--spacing-lg);
  line-height: 1.7;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-md);
  margin-bottom: var(--spacing-lg);
}

.contact-method {
  display: flex;
  align-items: center;
  gap: var(--spacing-sm);
  padding: var(--spacing-md);
  background: var(--color-bg);
  border-radius: 8px;
  text-decoration: none;
  color: var(--color-text);
  transition: all var(--transition-normal);
  border: 1px solid var(--color-border);
}

.contact-method:not(.not-link):hover {
  transform: translateX(5px);
  border-color: var(--color-accent);
  cursor: pointer;
}

.contact-method.not-link {
  cursor: default;
}

.contact-icon {
  font-size: 1.5rem;
}

.contact-text {
  font-weight: 500;
}
</style>