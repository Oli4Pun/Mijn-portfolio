<template>
  <section id="skills" class="section skills">
    <div class="container">
      <div class="section-header">
        <span class="section-number">03</span>
        <h2 class="section-title">Skills & Technologies</h2>
      </div>
      <div class="skills-grid">
        <div class="skill-category">
          <h3 class="skill-category-title">Programming</h3>
          <div class="skill-list">
            <div v-for="skill in programmingSkills" :key="skill.name" class="skill-item">
              <span class="skill-name">{{ skill.name }}</span>
              <div class="skill-bar">
                <div 
                  class="skill-progress" 
                  :style="{ width: isVisible ? skill.level + '%' : '0%' }"
                ></div>
              </div>
            </div>
          </div>
        </div>

        <div class="skill-category">
          <h3 class="skill-category-title">Core Strengths</h3>
          <ul class="strength-list">
            <li v-for="strength in strengths" :key="strength">{{ strength }}</li>
          </ul>
        </div>

        <div class="skill-category">
          <h3 class="skill-category-title">Certifications</h3>
          <ul class="cert-list">
            <li v-for="cert in certifications" :key="cert">{{ cert }}</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      isVisible: false,
      programmingSkills: [
        { name: 'C#', level: 85 },
        { name: 'JavaScript', level: 80 },
        { name: 'SQL', level: 75 },
        { name: 'HTML/CSS', level: 90 }
      ],
      strengths: [
        'Softwareontwikkeling',
        'Data-analyse',
        'Probleemoplossend vermogen',
        'Rustig onder druk',
        'Leergierig'
      ],
      certifications: [
        'Heftruck certificaat',
        'Reachtruck certificaat',
        'Rijbewijs B (auto)'
      ]
    }
  },
  mounted() {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            this.isVisible = true
            observer.disconnect()
          }
        })
      },
      {
        threshold: 0.3
      }
    )

    const skillsSection = this.$el
    if (skillsSection) {
      observer.observe(skillsSection)
    }
  }
}
</script>

<style scoped>
.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: var(--spacing-lg);
}

.skill-category {
  background: var(--color-surface);
  padding: var(--spacing-md);
  border-radius: 12px;
  border: 1px solid var(--color-border);
}

.skill-category-title {
  font-size: 1.25rem;
  font-weight: 700;
  margin-bottom: var(--spacing-md);
  color: var(--color-text);
}

.skill-list {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-md);
}

.skill-item {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-xs);
}

.skill-name {
  font-family: var(--font-mono);
  font-weight: 600;
  font-size: 0.9rem;
  color: var(--color-text);
}

.skill-bar {
  height: 8px;
  background: var(--color-border);
  border-radius: 4px;
  overflow: hidden;
}

.skill-progress {
  height: 100%;
  background: linear-gradient(90deg, var(--color-gradient-start), var(--color-gradient-end));
  border-radius: 4px;
  transition: width 1s ease;
}

.strength-list,
.cert-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: var(--spacing-sm);
}

.strength-list li,
.cert-list li {
  padding-left: var(--spacing-md);
  position: relative;
  color: var(--color-text-muted);
}

.strength-list li::before,
.cert-list li::before {
  content: '▹';
  position: absolute;
  left: 0;
  color: var(--color-accent);
  font-weight: bold;
}

@media (max-width: 768px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }
}
</style>