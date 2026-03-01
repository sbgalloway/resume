<template>
  <main class="page">
    <ThemeToggle />
    <div class="content">
      <h1 class="name">Sam Galloway</h1>
      <p class="title">Full Stack Developer</p>
      <nav aria-label="Profile links">
        <ul class="links">
          <li v-for="link in links" :key="link.label">
            <a
              :href="link.url"
              class="link-card"
              target="_blank"
              rel="noopener noreferrer"
            >
              <span class="link-icon" v-html="link.icon"></span>
              <span class="link-label">{{ link.label }}</span>
            </a>
          </li>
        </ul>
      </nav>
    </div>
  </main>
</template>

<script setup>
import ThemeToggle from './ThemeToggle.vue'

const links = [
  {
    label: 'GitHub',
    url: 'https://github.com/sbgalloway',
    icon: '<svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>',
  },
  {
    label: 'LinkedIn',
    url: '#',
    icon: '<svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>',
  },
  {
    label: 'YouTube',
    url: '#',
    icon: '<svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/></svg>',
  },
  {
    label: 'Bluesky',
    url: '#',
    icon: '<svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M12 10.8c-1.087-2.114-4.046-6.053-6.798-7.995C2.566.944 1.561 1.266.902 1.565.139 1.908 0 3.08 0 3.768c0 .69.378 5.65.596 6.449.76 2.784 3.471 3.7 5.998 3.435-.363.065-.728.108-1.094.126-2.07.1-4.267.96-1.595 3.386C6.45 19.558 8.70 20.935 10.54 17.58c.428-.783.793-1.708 1.46-1.708.667 0 1.032.925 1.46 1.708 1.84 3.355 4.09 1.978 6.635-.416 2.672-2.426.475-3.287-1.595-3.386a10.683 10.683 0 0 1-1.094-.126c2.527.265 5.239-.65 5.998-3.435C23.622 9.418 24 4.458 24 3.768c0-.69-.139-1.861-.902-2.203-.659-.3-1.664-.62-4.3 1.24C16.046 4.748 13.087 8.687 12 10.8z"/></svg>',
  },
  {
    label: 'Employer',
    url: '#',
    icon: '<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="7" width="20" height="14" rx="2" ry="2"/><path d="M16 21V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v16"/></svg>',
  },
]
</script>

<style>
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root,
[data-theme="dark"] {
  --color-bg: #1a1a2e;
  --color-text: #e8e6e1;
  --color-text-muted: #9a9a9a;
  --color-surface: rgba(255, 255, 255, 0.05);
  --color-surface-hover: rgba(255, 255, 255, 0.1);
  --color-border: rgba(255, 255, 255, 0.08);
  --color-border-hover: rgba(255, 255, 255, 0.2);
  --color-accent: #7c8cf8;
}

[data-theme="light"] {
  --color-bg: #f5f4f0;
  --color-text: #2c2c2c;
  --color-text-muted: #6b6b6b;
  --color-surface: rgba(0, 0, 0, 0.03);
  --color-surface-hover: rgba(0, 0, 0, 0.07);
  --color-border: rgba(0, 0, 0, 0.08);
  --color-border-hover: rgba(0, 0, 0, 0.2);
  --color-accent: #4a5acf;
}

html,
body {
  height: 100%;
  background: var(--color-bg);
  color: var(--color-text);
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  transition: background 0.3s, color 0.3s;
}

#app {
  height: 100%;
}

@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    transition: none !important;
  }
}
</style>

<style scoped>
.page {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100%;
  padding: 2rem 1rem;
}

.content {
  text-align: center;
  width: 100%;
  max-width: 24rem;
}

.name {
  font-size: 2rem;
  font-weight: 600;
  letter-spacing: -0.02em;
  margin-bottom: 0.375rem;
}

.title {
  color: var(--color-text-muted);
  font-size: 1.05rem;
  margin-bottom: 2.5rem;
}

.links {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.625rem;
}

.link-card {
  display: flex;
  align-items: center;
  gap: 0.875rem;
  padding: 0.875rem 1.25rem;
  border: 1px solid var(--color-border);
  border-radius: 0.75rem;
  background: var(--color-surface);
  color: var(--color-text);
  text-decoration: none;
  transition: background 0.2s, border-color 0.2s, transform 0.2s;
}

.link-card:hover {
  background: var(--color-surface-hover);
  border-color: var(--color-border-hover);
  transform: translateY(-1px);
}

.link-card:focus-visible {
  outline: 2px solid var(--color-accent);
  outline-offset: 2px;
}

.link-icon {
  display: flex;
  align-items: center;
  flex-shrink: 0;
  color: var(--color-text-muted);
}

.link-label {
  font-size: 0.95rem;
  font-weight: 500;
}
</style>
