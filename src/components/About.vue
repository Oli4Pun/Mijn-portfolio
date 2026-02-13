<template>
  <section id="about" class="section about">
    <div class="container">
      <div class="section-header">
        <span class="section-number">01</span>
        <h2 class="section-title">About Me</h2>
      </div>
      <div class="about-grid">
        <div class="about-text">
          <p class="lead">{{ leadText }}</p>
          <p>{{ bodyText }}</p>
          <div class="about-info">
            <div v-for="info in infoItems" :key="info.label" class="info-item">
              <span class="info-label">{{ info.label }}</span>
              <span class="info-value">{{ info.value }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      leadText: 'In staat om rustig en gestructureerd te werken, ook onder druk. Gedreven om nieuwe technologieën te leren en toe te passen in de praktijk.',
      bodyText: 'Klaar om waarde toe te voegen binnen een dynamisch team en verder te groeien als ontwikkelaar. Met ervaring als scoutsleider heb ik geleerd om te leiden, samen te werken en creatief problemen op te lossen.',
      infoItems: [
        { label: 'Location', value: 'Bilzen, Belgium' },
        { label: 'Education', value: 'Graduaat Programmeren, PXL Hasselt' },
        { label: 'Languages', value: 'Nederlands (Native), English (Proficient)' }
      ]
    }
  }
}
</script>

<style scoped>
.about-grid {
  display: grid;
  gap: var(--spacing-lg);
}

.about-text .lead {
  font-size: 1.25rem;
  line-height: 1.8;
  color: var(--color-text);
  margin-bottom: var(--spacing-md);
}

.about-text p {
  color: var(--color-text-muted);
  margin-bottom: var(--spacing-md);
  line-height: 1.8;
}

.about-info {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--spacing-md);
  margin-top: var(--spacing-lg);
}

.info-item {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-xs);
  padding: var(--spacing-md);
  background: var(--color-surface);
  border-radius: 8px;
  border-left: 3px solid var(--color-accent);
  transition: transform var(--transition-normal);
}

.info-item:hover {
  transform: translateX(5px);
}

.info-label {
  font-family: var(--font-mono);
  font-size: 0.85rem;
  color: var(--color-text-muted);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.info-value {
  font-weight: 600;
  color: var(--color-text);
}
</style>