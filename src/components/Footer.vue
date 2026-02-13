<template>
  <footer class="footer">
    <div class="container">
      <p>&copy; {{ currentYear }} Olivier Punie. All rights reserved.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      currentYear: new Date().getFullYear()
    }
  }
}
</script>

<style scoped>
.footer {
  padding: var(--spacing-md);
  text-align: center;
  color: var(--color-text-muted);
  border-top: 1px solid var(--color-border);
  background: var(--color-surface);
}
</style>