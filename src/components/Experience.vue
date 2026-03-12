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
        
        <div class="project-list">
          <div v-for="project in projects" :key="project.title" class="project-item">
            <h4 class="project-title">{{ project.title }}</h4>
            <p class="project-description">{{ project.description }}</p>
            <a 
              :href="project.github" 
              class="github-link"
              target="_blank"
              rel="noopener noreferrer"
            >
              <svg width="18" height="18" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
              </svg>
              View on GitHub
            </a>
          </div>
        </div>

        <div class="github-profile">
          <a 
            href="https://github.com/Oli4Pun" 
            class="github-profile-link"
            target="_blank"
            rel="noopener noreferrer"
          >
            Bekijk al mijn projecten op GitHub →
          </a>
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
      ],
      
      projects: [
        {
          title: 'Portfolio Website',
          description: 'Moderne portfolio website gebouwd met Vue.js, met een uniek geometrisch design en smooth animaties.',
          github: 'https://github.com/Oli4Pun/Mijn-portfolio'
        },
        {
          title: 'Blazor Webshop',
          description: 'PXLPRO2025Shoppers12 is een webshop applicatie ontwikkeld met Blazor en .NET.',
          github: 'https://github.com/Oli4Pun/Project-Web2'
        },
        {
          title: 'Encryptietool',
          description: 'EncryptionTool is een applicatie ontwikkeld in C# en .NET waarmee bestanden veilig versleuteld en ontsleuteld kunnen worden.',
          github: 'https://github.com/Oli4Pun/PXLEncryptionTool'
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

.project-list {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-md);
  margin-bottom: var(--spacing-lg);
}

.project-item {
  background: var(--color-surface);
  padding: var(--spacing-md);
  border-radius: 12px;
  border: 1px solid var(--color-border);
  transition: all var(--transition-normal);
}

.project-item:hover {
  border-color: var(--color-accent);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
}

.project-title {
  font-size: 1.25rem;
  font-weight: 700;
  color: var(--color-text);
  margin-bottom: var(--spacing-xs);
}

.project-description {
  color: var(--color-text-muted);
  line-height: 1.6;
  margin-bottom: var(--spacing-sm);
}

.github-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  font-weight: 600;
  font-size: 0.95rem;
  color: var(--color-accent);
  text-decoration: none;
  transition: all var(--transition-fast);
}

.github-link:hover {
  color: var(--color-accent-light);
  gap: 0.75rem;
}

.github-link svg {
  width: 18px;
  height: 18px;
}

.github-profile {
  margin-top: var(--spacing-lg);
  padding: var(--spacing-md);
  background: var(--color-surface);
  border-radius: 12px;
  text-align: center;
  border: 2px dashed var(--color-border);
}

.github-profile-link {
  display: inline-block;
  font-weight: 600;
  font-size: 1rem;
  color: var(--color-accent);
  text-decoration: none;
  transition: all var(--transition-fast);
}

.github-profile-link:hover {
  color: var(--color-accent-light);
}

@media (max-width: 768px) {
  .timeline {
    padding-left: var(--spacing-md);
  }
}
</style>