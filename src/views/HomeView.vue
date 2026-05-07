<template>
  <main class="home">
    <!-- Left: Text Content -->
    <div class="home__content">
      <!-- Greeting -->
      <div class="home__greeting">
        <span class="greeting-line"></span>
        <span class="greeting-text">Hello World, I'm</span>
      </div>

      <!-- Name -->
      <h1 class="home__name">
        Ikhsan<br>
        <span class="home__name--accent">Pratama</span>
      </h1>

      <!-- Typewriter -->
      <div class="home__typewriter">
        <span class="typewriter-prefix">&gt;&nbsp;</span>
        <span ref="typewriter" class="typewriter-text">{{ txt }}</span>
        <span class="typewriter-cursor">|</span>
      </div>

      <!-- Description -->
      <p class="home__desc">
        Welcome to my personal website.
        <span class="wave">👋🏼</span>
      </p>

      <!-- CTA Buttons -->
      <div class="home__ctas">
        <a href="mailto:ikhsan@example.com" class="cta-primary">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5">
            <path d="M5 12h14M12 5l7 7-7 7"/>
          </svg>
          Hire Me
        </a>
        <a href="#" class="cta-secondary">
          <svg width="15" height="15" viewBox="0 0 24 24" fill="currentColor">
            <path fill-rule="evenodd" d="M5.625 1.5H9a3.75 3.75 0 013.75 3.75v1.875c0 1.036.84 1.875 1.875 1.875H16.5a3.75 3.75 0 013.75 3.75v7.875c0 1.035-.84 1.875-1.875 1.875H5.625a1.875 1.875 0 01-1.875-1.875V3.375c0-1.036.84-1.875 1.875-1.875zm5.845 17.03a.75.75 0 001.06 0l3-3a.75.75 0 10-1.06-1.06l-1.72 1.72V12a.75.75 0 00-1.5 0v4.19l-1.72-1.72a.75.75 0 00-1.06 1.06l3 3z" clip-rule="evenodd"/>
            <path d="M14.25 5.25a5.23 5.23 0 00-1.279-3.434 9.768 9.768 0 016.963 6.963A5.23 5.23 0 0016.5 7.5h-1.875a.375.375 0 01-.375-.375V5.25z"/>
          </svg>
          Resume
        </a>
      </div>

      <!-- Social Links -->
      <div class="home__socials">
        <a href="https://github.com/HENGKER-MAGANG" target="_blank" class="social-link" aria-label="GitHub">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/>
          </svg>
        </a>
        <a href="#" target="_blank" class="social-link" aria-label="LinkedIn">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="currentColor">
            <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
          </svg>
        </a>
        <a href="#" target="_blank" class="social-link" aria-label="Instagram">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/>
          </svg>
        </a>
      </div>
    </div>

    <!-- Right: Avatar -->
    <div class="home__avatar-wrap">
      <!-- Decorative ring -->
      <div class="avatar-ring"></div>
      <div class="avatar-ring avatar-ring--2"></div>

      <!-- Code badge floating -->
      <div class="avatar-badge avatar-badge--top">
        <span class="badge-dot"></span>
        <span>Available for work</span>
      </div>

      <div class="avatar-container">
        <img
          alt="Ikhsan Pratama"
          fetchpriority="high"
          decoding="async"
          class="avatar-img"
          src="../../meeeee.jpg"
        />
      </div>

      <!-- Stack badge -->
      <div class="avatar-badge avatar-badge--bot">
        <span class="badge-icon">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
        </span>
        <span>Vue · Laravel · JS</span>
      </div>
    </div>

    <!-- Scroll indicator -->
    <div class="scroll-hint">
      <div class="scroll-hint__mouse">
        <div class="scroll-hint__dot"></div>
      </div>
      <span>Scroll</span>
    </div>
  </main>
</template>

<script>
export default {
  name: 'HomeView',
  data() {
    return {
      toRotate: ['Web Developer', 'Full-stack Engineer', 'Informatics Student', 'Tech Enthusiast'],
      period: 2000,
      txt: '',
      loopNum: 0,
      isDeleting: false,
    };
  },
  mounted() {
    this.$nextTick(() => {
      this.tick();
    });
  },
  methods: {
    tick() {
      const typewriter = this.$refs.typewriter;
      if (!typewriter) return;

      const i = this.loopNum % this.toRotate.length;
      const fullTxt = this.toRotate[i];

      this.txt = this.isDeleting
        ? fullTxt.substring(0, this.txt.length - 1)
        : fullTxt.substring(0, this.txt.length + 1);

      typewriter.textContent = this.txt;

      let delta = 200 - Math.random() * 100;
      if (this.isDeleting) delta /= 2;

      if (!this.isDeleting && this.txt === fullTxt) {
        delta = this.period;
        this.isDeleting = true;
      } else if (this.isDeleting && this.txt === '') {
        this.isDeleting = false;
        this.loopNum++;
        delta = 500;
      }

      setTimeout(() => this.tick(), delta);
    },
  },
};
</script>

<style scoped>
/* ─── Layout ────────────────────────────────────────────────── */
.home {
  max-width: 1200px;
  margin: 0 auto;
  padding: 60px 32px 40px;
  min-height: calc(100vh - 72px);
  display: flex;
  flex-direction: column-reverse;
  align-items: center;
  justify-content: center;
  gap: 52px;
  position: relative;
}

@media (min-width: 768px) {
  .home {
    flex-direction: row;
    justify-content: space-between;
    padding: 0 48px;
    gap: 40px;
  }
}

/* ─── Left Content ───────────────────────────────────────────── */
.home__content {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 20px;
  flex: 1;
  max-width: 520px;
  animation: slideInLeft 0.7s cubic-bezier(0.16, 1, 0.3, 1) 0.1s both;
}

@media (min-width: 768px) {
  .home__content {
    align-items: flex-start;
    text-align: left;
  }
}

/* Greeting */
.home__greeting {
  display: flex;
  align-items: center;
  gap: 10px;
  font-family: var(--font-mono);
  font-size: 0.78rem;
  color: var(--gold);
  letter-spacing: 0.12em;
  text-transform: uppercase;
  opacity: 0;
  animation: fadeUp 0.5s ease forwards 0.2s;
}
.greeting-line {
  display: block;
  width: 28px;
  height: 1px;
  background: var(--gold);
  opacity: 0.6;
}

/* Name */
.home__name {
  font-family: var(--font-sans);
  font-size: clamp(2.6rem, 6vw, 4.2rem);
  font-weight: 800;
  line-height: 1.1;
  letter-spacing: -0.03em;
  color: var(--text);
  opacity: 0;
  animation: fadeUp 0.6s cubic-bezier(0.16, 1, 0.3, 1) forwards 0.35s;
}
.home__name--accent {
  color: var(--gold);
  position: relative;
  display: inline-block;
}
.home__name--accent::after {
  content: '';
  position: absolute;
  left: 0; bottom: -4px;
  width: 100%; height: 3px;
  background: linear-gradient(90deg, var(--gold), transparent);
  border-radius: 2px;
}

/* Typewriter */
.home__typewriter {
  display: flex;
  align-items: center;
  gap: 2px;
  font-family: var(--font-mono);
  font-size: clamp(0.9rem, 2.2vw, 1.15rem);
  font-weight: 500;
  color: var(--text-muted);
  background: rgba(255, 219, 112, 0.05);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 8px 16px;
  width: fit-content;
  opacity: 0;
  animation: fadeUp 0.5s ease forwards 0.55s;
}
.typewriter-prefix {
  color: var(--gold);
  font-weight: 700;
  margin-right: 2px;
}
.typewriter-text { color: var(--text); }
.typewriter-cursor {
  color: var(--gold);
  animation: blink 1s step-end infinite;
  margin-left: 1px;
}
@keyframes blink {
  0%, 100% { opacity: 1; }
  50%       { opacity: 0; }
}

/* Description */
.home__desc {
  font-size: 0.95rem;
  color: var(--text-muted);
  line-height: 1.6;
  max-width: 380px;
  opacity: 0;
  animation: fadeUp 0.5s ease forwards 0.7s;
}

/* Wave emoji */
.wave {
  animation: wave-animation 2.5s infinite;
  transform-origin: 70% 70%;
  display: inline-block;
}
@keyframes wave-animation {
  0%   { transform: rotate(0deg); }
  10%  { transform: rotate(14deg); }
  20%  { transform: rotate(-8deg); }
  30%  { transform: rotate(14deg); }
  40%  { transform: rotate(-4deg); }
  50%  { transform: rotate(10deg); }
  60%, 100% { transform: rotate(0deg); }
}

/* CTA Buttons */
.home__ctas {
  display: flex;
  align-items: center;
  gap: 12px;
  flex-wrap: wrap;
  justify-content: center;
  opacity: 0;
  animation: fadeUp 0.5s ease forwards 0.85s;
}
@media (min-width: 768px) {
  .home__ctas { justify-content: flex-start; }
}

.cta-primary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 11px 24px;
  border-radius: 50px;
  background: var(--gold);
  color: #0d0d0d;
  font-size: 0.85rem;
  font-weight: 700;
  font-family: var(--font-sans);
  letter-spacing: 0.04em;
  text-decoration: none;
  text-transform: uppercase;
  transition: background 0.25s, transform 0.3s cubic-bezier(0.16,1,0.3,1), box-shadow 0.3s;
}
.cta-primary:hover {
  background: #ffe99a;
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(255, 219, 112, 0.25);
}
.cta-primary svg { transition: transform 0.25s; }
.cta-primary:hover svg { transform: translateX(3px); }

.cta-secondary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 10px 22px;
  border-radius: 50px;
  background: transparent;
  border: 1px solid var(--border);
  color: var(--text-muted);
  font-size: 0.85rem;
  font-weight: 600;
  font-family: var(--font-sans);
  letter-spacing: 0.04em;
  text-decoration: none;
  text-transform: uppercase;
  transition: color 0.25s, border-color 0.25s, background 0.25s, transform 0.3s cubic-bezier(0.16,1,0.3,1);
}
.cta-secondary:hover {
  color: var(--gold);
  border-color: var(--gold-dim);
  background: var(--gold-glow);
  transform: translateY(-3px);
}

/* Socials */
.home__socials {
  display: flex;
  align-items: center;
  gap: 10px;
  opacity: 0;
  animation: fadeUp 0.5s ease forwards 1s;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 38px; height: 38px;
  border-radius: 10px;
  background: rgba(255,255,255,0.04);
  border: 1px solid var(--border);
  color: var(--text-muted);
  text-decoration: none;
  transition: color 0.25s, background 0.25s, border-color 0.25s, transform 0.3s cubic-bezier(0.16,1,0.3,1);
}
.social-link:hover {
  color: var(--gold);
  background: var(--gold-glow);
  border-color: var(--gold-dim);
  transform: translateY(-3px);
}

/* ─── Right: Avatar ──────────────────────────────────────────── */
.home__avatar-wrap {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  animation: slideInRight 0.7s cubic-bezier(0.16, 1, 0.3, 1) 0.2s both;
}

/* Decorative rings */
.avatar-ring {
  position: absolute;
  border-radius: 50%;
  border: 1px dashed rgba(255, 219, 112, 0.18);
  animation: spin 22s linear infinite;
  pointer-events: none;
}
.avatar-ring {
  width: 320px; height: 320px;
}
.avatar-ring--2 {
  width: 380px; height: 380px;
  border-style: dotted;
  border-color: rgba(255, 219, 112, 0.08);
  animation-direction: reverse;
  animation-duration: 35s;
}
@media (min-width: 768px) {
  .avatar-ring   { width: 400px; height: 400px; }
  .avatar-ring--2{ width: 460px; height: 460px; }
}
@keyframes spin {
  from { transform: rotate(0deg); }
  to   { transform: rotate(360deg); }
}

/* Avatar image */
.avatar-container {
  position: relative;
  z-index: 2;
  border-radius: 50%;
  padding: 5px;
  background: linear-gradient(135deg, var(--gold) 0%, rgba(255,219,112,0.2) 50%, transparent 100%);
}
.avatar-img {
  width: 200px; height: 200px;
  border-radius: 50%;
  object-fit: cover;
  display: block;
  background: var(--bg-card);
  box-shadow:
    0 0 60px rgba(255, 219, 112, 0.15),
    0 20px 60px rgba(0,0,0,0.5);
}
@media (min-width: 480px) {
  .avatar-img { width: 240px; height: 240px; }
}
@media (min-width: 768px) {
  .avatar-img { width: 300px; height: 300px; }
}
@media (min-width: 1024px) {
  .avatar-img { width: 340px; height: 340px; }
}

/* Floating badges */
.avatar-badge {
  position: absolute;
  z-index: 3;
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 7px 14px;
  border-radius: 50px;
  background: var(--bg-card);
  border: 1px solid var(--border);
  font-size: 0.72rem;
  font-family: var(--font-mono);
  color: var(--text-muted);
  white-space: nowrap;
  backdrop-filter: blur(12px);
  box-shadow: 0 8px 32px rgba(0,0,0,0.4);
}
.avatar-badge--top {
  top: 12px; right: -12px;
  animation: badgeFloat 3s ease-in-out infinite;
}
.avatar-badge--bot {
  bottom: 12px; left: -12px;
  animation: badgeFloat 3.5s ease-in-out infinite reverse;
}
@keyframes badgeFloat {
  0%, 100% { transform: translateY(0); }
  50%       { transform: translateY(-6px); }
}
.badge-dot {
  width: 7px; height: 7px;
  border-radius: 50%;
  background: #4ade80;
  box-shadow: 0 0 6px #4ade80;
  animation: pulse 2s ease-in-out infinite;
}
@keyframes pulse {
  0%, 100% { opacity: 1; }
  50%       { opacity: 0.5; }
}
.badge-icon {
  color: var(--gold);
  display: flex;
}

/* ─── Scroll Hint ─────────────────────────────────────────────── */
.scroll-hint {
  position: absolute;
  bottom: 28px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 6px;
  font-family: var(--font-mono);
  font-size: 0.6rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--text-muted);
  opacity: 0;
  animation: fadeUp 0.5s ease forwards 1.3s;
}
@media (max-width: 767px) { .scroll-hint { display: none; } }

.scroll-hint__mouse {
  width: 22px; height: 34px;
  border: 1.5px solid rgba(255,255,255,0.2);
  border-radius: 12px;
  display: flex;
  justify-content: center;
  padding-top: 6px;
}
.scroll-hint__dot {
  width: 3px; height: 6px;
  background: var(--gold);
  border-radius: 2px;
  animation: scrollDot 1.8s ease-in-out infinite;
}
@keyframes scrollDot {
  0%   { transform: translateY(0); opacity: 1; }
  80%  { transform: translateY(10px); opacity: 0; }
  100% { transform: translateY(0); opacity: 0; }
}

/* ─── Entry animations ───────────────────────────────────────── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}
@keyframes slideInLeft {
  from { opacity: 0; transform: translateX(-40px); }
  to   { opacity: 1; transform: translateX(0); }
}
@keyframes slideInRight {
  from { opacity: 0; transform: translateX(40px); }
  to   { opacity: 1; transform: translateX(0); }
}
</style>