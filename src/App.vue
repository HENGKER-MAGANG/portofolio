<template>
  <div class="app-wrapper">
    <!-- Noise texture overlay -->
    <div class="noise-overlay"></div>

    <!-- Ambient glow blobs -->
    <div class="ambient-blob blob-1"></div>
    <div class="ambient-blob blob-2"></div>

    <!-- Desktop Navbar -->
    <nav class="navbar" :class="{ 'navbar--scrolled': isScrolled }">
      <div class="navbar__inner">
        <!-- Logo -->
        <button @click="redirectToHome" class="navbar__logo">
          <span class="logo-bracket">{</span>
          <span class="logo-name">Ikhsan</span>
          <span class="logo-dot">.</span>
          <span class="logo-fn">dev</span>
          <span class="logo-bracket">}</span>
          <span class="logo-cursor">_</span>
        </button>

        <!-- Desktop Nav Links -->
        <ul class="navbar__links">
          <li v-for="(link, i) in navLinks" :key="link.path" :style="{ '--i': i }">
            <router-link :to="link.path" class="nav-link">
              <span class="nav-link__num">0{{ i + 1 }}.</span>
              <span class="nav-link__label">{{ link.label }}</span>
            </router-link>
          </li>
        </ul>

        <!-- GitHub + Hire Me -->
        <div class="navbar__actions">
          <a href="https://github.com/HENGKER-MAGANG" target="_blank" class="github-btn" aria-label="GitHub">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/>
            </svg>
          </a>
          <a href="mailto:ikhsan@example.com" class="hire-btn">
            <span>Hire Me</span>
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5">
              <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
          </a>
        </div>
      </div>
    </nav>

    <!-- Page Content -->
    <main class="main-content">
      <router-view v-slot="{ Component }">
        <transition name="page" mode="out-in">
          <component :is="Component" />
        </transition>
      </router-view>
    </main>

    <!-- Mobile Bottom Nav -->
    <footer class="mobile-nav">
      <nav class="mobile-nav__inner">
        <router-link
          v-for="link in navLinks"
          :key="link.path"
          :to="link.path"
          class="mobile-nav__item"
        >
          <span class="mobile-nav__icon" v-html="link.icon"></span>
          <span class="mobile-nav__label">{{ link.label }}</span>
        </router-link>
      </nav>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      isScrolled: false,
      navLinks: [
        {
          path: '/',
          label: 'Home',
          icon: `<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 9l9-7 9 7v11a2 2 0 01-2 2H5a2 2 0 01-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>`
        },
        {
          path: '/about',
          label: 'About',
          icon: `<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="8" r="4"/><path d="M4 20c0-4 3.6-7 8-7s8 3 8 7"/></svg>`
        },
        {
          path: '/portfolio',
          label: 'Portfolio',
          icon: `<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg>`
        },
        {
          path: '/blog',
          label: 'Blog',
          icon: `<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 20h9"/><path d="M16.5 3.5a2.121 2.121 0 013 3L7 19l-4 1 1-4L16.5 3.5z"/></svg>`
        },
      ]
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    redirectToHome() {
      this.$router.push('/')
    },
    handleScroll() {
      this.isScrolled = window.scrollY > 20
    }
  }
}
</script>

<style>
/* ─── Reset & Base ─────────────────────────────────────────── */
*, *::before, *::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --bg:        #0d0d0d;
  --bg-card:   #161616;
  --bg-glass:  rgba(22, 22, 22, 0.75);
  --border:    rgba(255, 219, 112, 0.12);
  --gold:      #ffdb70;
  --gold-dim:  rgba(255, 219, 112, 0.55);
  --gold-glow: rgba(255, 219, 112, 0.18);
  --text:      #e8e8e0;
  --text-muted:#888880;
  --font-mono: 'JetBrains Mono', 'Fira Code', 'Cascadia Code', monospace;
  --font-sans: 'Syne', 'Outfit', sans-serif;
  --nav-h:     72px;
  --radius:    12px;
  --ease-out:  cubic-bezier(0.16, 1, 0.3, 1);
}

html { scroll-behavior: smooth; }

body {
  font-family: var(--font-sans);
  background: var(--bg);
  color: var(--text);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  min-height: 100vh;
  overflow-x: hidden;
}

/* Google Fonts import */
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap');

/* ─── Scrollbar ─────────────────────────────────────────────── */
::-webkit-scrollbar { width: 4px; }
::-webkit-scrollbar-track { background: #111; }
::-webkit-scrollbar-thumb { background: var(--gold); border-radius: 4px; }

/* ─── App Wrapper ──────────────────────────────────────────── */
.app-wrapper {
  position: relative;
  min-height: 100vh;
}

/* ─── Noise Overlay ────────────────────────────────────────── */
.noise-overlay {
  pointer-events: none;
  position: fixed;
  inset: 0;
  z-index: 999;
  opacity: 0.028;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
  background-size: 200px;
}

/* ─── Ambient Blobs ────────────────────────────────────────── */
.ambient-blob {
  pointer-events: none;
  position: fixed;
  border-radius: 50%;
  filter: blur(100px);
  z-index: 0;
  animation: blobFloat 12s ease-in-out infinite alternate;
}
.blob-1 {
  width: 480px; height: 480px;
  top: -120px; left: -100px;
  background: radial-gradient(circle, rgba(255,219,112,0.07) 0%, transparent 70%);
  animation-duration: 14s;
}
.blob-2 {
  width: 360px; height: 360px;
  bottom: 10%; right: -80px;
  background: radial-gradient(circle, rgba(255,180,60,0.05) 0%, transparent 70%);
  animation-duration: 10s;
  animation-direction: alternate-reverse;
}
@keyframes blobFloat {
  from { transform: translate(0, 0) scale(1); }
  to   { transform: translate(30px, 20px) scale(1.08); }
}

/* ─── Navbar ───────────────────────────────────────────────── */
.navbar {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  height: var(--nav-h);
  transition: background 0.4s var(--ease-out), border-color 0.4s, box-shadow 0.4s;
  border-bottom: 1px solid transparent;
}
.navbar--scrolled {
  background: var(--bg-glass);
  backdrop-filter: blur(20px) saturate(1.4);
  -webkit-backdrop-filter: blur(20px) saturate(1.4);
  border-bottom-color: var(--border);
  box-shadow: 0 8px 40px rgba(0,0,0,0.5);
}

.navbar__inner {
  max-width: 1200px;
  margin: 0 auto;
  height: 100%;
  padding: 0 32px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
}

/* Logo */
.navbar__logo {
  background: none;
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 1px;
  font-family: var(--font-mono);
  font-size: 1.05rem;
  font-weight: 600;
  letter-spacing: -0.02em;
  padding: 6px 0;
  color: var(--text);
  transition: transform 0.3s var(--ease-out);
  animation: fadeSlideDown 0.6s var(--ease-out) both;
}
.navbar__logo:hover { transform: translateY(-1px); }
.logo-bracket { color: var(--gold-dim); }
.logo-name    { color: var(--text); margin: 0 1px; }
.logo-dot     { color: var(--gold); }
.logo-fn      { color: var(--gold); }
.logo-cursor  {
  color: var(--gold);
  animation: blink 1.1s step-end infinite;
  margin-left: 1px;
}
@keyframes blink {
  0%, 100% { opacity: 1; }
  50%       { opacity: 0; }
}

/* Nav Links */
.navbar__links {
  display: none;
  list-style: none;
  gap: 6px;
}
@media (min-width: 768px) {
  .navbar__links { display: flex; }
}

.navbar__links li {
  animation: fadeSlideDown 0.6s var(--ease-out) calc(var(--i) * 80ms + 100ms) both;
}

.nav-link {
  display: flex;
  align-items: center;
  gap: 5px;
  padding: 7px 14px;
  border-radius: 8px;
  text-decoration: none;
  color: var(--text-muted);
  font-size: 0.82rem;
  font-weight: 500;
  font-family: var(--font-sans);
  letter-spacing: 0.02em;
  transition: color 0.25s, background 0.25s;
  position: relative;
}
.nav-link:hover {
  color: var(--text);
  background: rgba(255,255,255,0.04);
}
.nav-link.router-link-exact-active {
  color: var(--gold);
}
.nav-link.router-link-exact-active::after {
  content: '';
  position: absolute;
  bottom: 4px;
  left: 50%;
  transform: translateX(-50%);
  width: 16px;
  height: 2px;
  background: var(--gold);
  border-radius: 2px;
}

.nav-link__num {
  font-family: var(--font-mono);
  font-size: 0.68rem;
  color: var(--gold-dim);
  transition: color 0.25s;
}
.nav-link:hover .nav-link__num,
.nav-link.router-link-exact-active .nav-link__num {
  color: var(--gold);
}

/* Actions */
.navbar__actions {
  display: none;
  align-items: center;
  gap: 12px;
  animation: fadeSlideDown 0.6s var(--ease-out) 450ms both;
}
@media (min-width: 768px) {
  .navbar__actions { display: flex; }
}

.github-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 36px; height: 36px;
  border-radius: 50%;
  background: rgba(255,255,255,0.05);
  border: 1px solid var(--border);
  color: var(--text-muted);
  text-decoration: none;
  transition: color 0.25s, background 0.25s, border-color 0.25s, transform 0.3s var(--ease-out);
}
.github-btn:hover {
  color: var(--gold);
  background: var(--gold-glow);
  border-color: var(--gold-dim);
  transform: translateY(-2px);
}

.hire-btn {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  padding: 8px 18px;
  border-radius: 50px;
  background: var(--gold);
  color: #0d0d0d;
  font-size: 0.8rem;
  font-weight: 700;
  font-family: var(--font-sans);
  letter-spacing: 0.04em;
  text-decoration: none;
  text-transform: uppercase;
  transition: background 0.25s, transform 0.3s var(--ease-out), box-shadow 0.3s;
  box-shadow: 0 0 0 0 var(--gold-glow);
}
.hire-btn:hover {
  background: #ffe99a;
  transform: translateY(-2px);
  box-shadow: 0 6px 24px var(--gold-glow);
}
.hire-btn svg { transition: transform 0.25s; }
.hire-btn:hover svg { transform: translateX(3px); }

/* ─── Main Content ─────────────────────────────────────────── */
.main-content {
  position: relative;
  z-index: 1;
  padding-top: var(--nav-h);
  padding-bottom: 80px; /* space for mobile nav */
  min-height: 100vh;
}
@media (min-width: 768px) {
  .main-content { padding-bottom: 0; }
}

/* ─── Page Transitions ─────────────────────────────────────── */
.page-enter-active,
.page-leave-active {
  transition: opacity 0.28s ease, transform 0.28s var(--ease-out);
}
.page-enter-from {
  opacity: 0;
  transform: translateY(14px);
}
.page-leave-to {
  opacity: 0;
  transform: translateY(-8px);
}

/* ─── Mobile Bottom Nav ────────────────────────────────────── */
.mobile-nav {
  display: block;
  position: fixed;
  bottom: 0; left: 0; right: 0;
  z-index: 100;
  background: var(--bg-glass);
  backdrop-filter: blur(20px) saturate(1.4);
  -webkit-backdrop-filter: blur(20px) saturate(1.4);
  border-top: 1px solid var(--border);
  padding-bottom: env(safe-area-inset-bottom, 0px);
}
@media (min-width: 768px) {
  .mobile-nav { display: none; }
}

.mobile-nav__inner {
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 10px 8px;
}

.mobile-nav__item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3px;
  padding: 6px 16px;
  border-radius: 10px;
  text-decoration: none;
  color: var(--text-muted);
  font-size: 0.65rem;
  font-weight: 500;
  letter-spacing: 0.04em;
  transition: color 0.22s, background 0.22s, transform 0.22s var(--ease-out);
}
.mobile-nav__item:hover,
.mobile-nav__item.router-link-exact-active {
  color: var(--gold);
  transform: translateY(-2px);
}
.mobile-nav__item.router-link-exact-active {
  background: var(--gold-glow);
}
.mobile-nav__icon { line-height: 0; }
.mobile-nav__label { text-transform: uppercase; }

/* ─── Entry Animations ─────────────────────────────────────── */
@keyframes fadeSlideDown {
  from { opacity: 0; transform: translateY(-12px); }
  to   { opacity: 1; transform: translateY(0); }
}
</style>