<template>
  <section id="work" class="section work">
    <div class="container">
      <div class="section-header">
        <span class="section-number">02</span>
        <h2 class="section-title">Experience</h2>
      </div>
      
      <div class="timeline">
        <div v-for="item in experiences" :key="item.title" class="timeline-item">
          <div class="timeline-date">{{ item.date }}</div>
          <div class="timeline-content">
            <h3 class="timeline-title">{{ item.title }}</h3>
            <div class="timeline-company">{{ item.company }}</div>
            <p class="timeline-description">{{ item.description }}</p>
          </div>
        </div>
      </div>

      <div class="projects-section">
        <h3 class="projects-heading">Projects</h3>
        <div class="projects-placeholder">
          <p class="placeholder-text">
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Experience',
  data() {
    return {
      experiences: [
        {
          date: '2016 - 2024',
          title: 'Scoutsleider',
          company: 'Scouts Schorave, Bilzen',
          description: 'Leiderschapservaring door het begeleiden van groepen jongeren. Ontwikkelde sterke communicatieve vaardigheden, teamwork en probleemoplossend vermogen.'
        },
        {
          date: '2021 - 2023',
          title: 'Order Picker',
          company: 'H.ESSERS, Genk',
          description: 'Nauwkeurig en efficiënt werken in een dynamische logistieke omgeving. Ervaring met gestructureerd werken onder tijdsdruk.'
        }
      ]
    }
  }
}
</script>

<style scoped>
.timeline {
  position: relative;
  padding-left: var(--spacing-lg);
  margin-bottom: var(--spacing-xl);
}

.timeline::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 2px;
  background: var(--color-border);
}

.timeline-item {
  position: relative;
  margin-bottom: var(--spacing-lg);
  padding-left: var(--spacing-md);
}

.timeline-item::before {
  content: '';
  position: absolute;
  left: -34px;
  top: 4px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: var(--color-accent);
  border: 3px solid var(--color-bg);
}

.timeline-date {
  font-family: var(--font-mono);
  font-size: 0.85rem;
  color: var(--color-accent);
  margin-bottom: var(--spacing-xs);
}

.timeline-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--color-text);
  margin-bottom: var(--spacing-xs);
}

.timeline-company {
  font-weight: 600;
  color: var(--color-text-muted);
  margin-bottom: var(--spacing-sm);
}

.timeline-description {
  color: var(--color-text-muted);
  line-height: 1.7;
}

.projects-section {
  margin-top: var(--spacing-xl);
}

.projects-heading {
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: var(--spacing-md);
  color: var(--color-text);
}

.projects-placeholder {
  padding: var(--spacing-lg);
  background: var(--color-surface);
  border: 2px dashed var(--color-border);
  border-radius: 12px;
  text-align: center;
}

.placeholder-text {
  color: var(--color-text-muted);
  line-height: 1.6;
}

@media (max-width: 768px) {
  .timeline {
    padding-left: var(--spacing-md);
  }
}
</style>