<script>
  let menuOpen = false;

  const navLinks = [
    { label: 'About', href: '#about' },
    { label: 'Platform', href: '#trading', badge: true },
    { label: 'Insights', href: '#faq' },
    { label: 'Contact', href: '#contact' }
  ];

  function toggleMenu() {
    menuOpen = !menuOpen;
  }

  function closeMenu() {
    menuOpen = false;
  }
</script>

<nav class="navbar {menuOpen ? 'open' : ''}">
  <div class="navbar-container">
    <div class="brand">
      <span class="logo">Stellar Pulse</span>
    </div>

    <button class="mobile-toggle" type="button" on:click={toggleMenu} aria-label="Toggle navigation">
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </button>

    <ul class="nav-links">
      {#each navLinks as link}
        <li>
          <a href={link.href} class="nav-link" on:click={closeMenu}>
            {link.label}
            {#if link.badge}
              <span class="chevron">▾</span>
            {/if}
          </a>
        </li>
      {/each}
    </ul>

    <div class="nav-actions">
      <button class="lang-button" type="button">ENG<span class="chevron">▾</span></button>
      <button class="btn login" type="button">Login</button>
      <button class="btn primary" type="button">Sign up</button>
    </div>
  </div>
</nav>

<style>
.navbar {
  position: fixed;
  inset: 0 auto auto 0;
  width: 100%;
  z-index: 20;
  background: rgba(7, 9, 24, 0.55);
  backdrop-filter: blur(22px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}

.navbar-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  padding: 1rem 1.5rem;
}

.brand .logo {
  font-weight: 700;
  letter-spacing: 0.12em;
  color: #ffffff;
  font-size: 1.1rem;
}

.mobile-toggle {
  display: none;
  border: none;
  background: transparent;
  padding: 0.5rem;
  border-radius: 999px;
  cursor: pointer;
}

.mobile-toggle:hover .bar {
  background: #ffffff;
}

.bar {
  display: block;
  width: 1.35rem;
  height: 2px;
  background: rgba(255, 255, 255, 0.9);
  margin: 0.24rem 0;
  transition: transform 0.2s ease, opacity 0.2s ease;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 1.8rem;
  margin: 0;
  padding: 0;
}

.nav-link {
  display: inline-flex;
  align-items: center;
  gap: 0.3rem;
  color: rgba(255, 255, 255, 0.82);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.2s ease, transform 0.2s ease;
}

.nav-link:hover {
  color: #ffffff;
  transform: translateY(-1px);
}

.chevron {
  font-size: 0.76rem;
  color: rgba(255, 255, 255, 0.65);
}

.nav-actions {
  display: flex;
  align-items: center;
  gap: 0.85rem;
}

.lang-button,
.btn {
  border: none;
  border-radius: 999px;
  cursor: pointer;
  font-size: 0.88rem;
  padding: 0.85rem 1.25rem;
  font-weight: 600;
  display: inline-flex;
  align-items: center;
  gap: 0.35rem;
}

.lang-button {
  background: rgba(255, 255, 255, 0.07);
  color: #d9dcff;
  border: 1px solid rgba(255, 255, 255, 0.08);
}

.btn.login {
  background: rgba(255, 255, 255, 0.05);
  color: #f7f8ff;
  border: 1px solid rgba(255, 255, 255, 0.12);
}

.btn.primary {
  background: linear-gradient(135deg, #0e75f1, #0de7ef);
  color: #ffffff;
  box-shadow: 0 18px 40px rgba(74, 185, 255, 0.22);
}

@media (max-width: 900px) {
  .mobile-toggle {
    display: inline-flex;
  }

  .nav-links,
  .nav-actions {
    display: none;
    width: 100%;
  }

  .navbar.open .nav-links,
  .navbar.open .nav-actions {
    display: flex;
  }

  .nav-links {
    flex-direction: column;
    align-items: center;
    gap: 1rem;
    margin-top: 1rem;
    padding: 1rem 0;
    border-top: 1px solid rgba(255, 255, 255, 0.08);
  }

  .nav-actions {
    flex-direction: column;
    align-items: stretch;
    gap: 0.9rem;
    padding: 1rem 0 0;
    border-top: 1px solid rgba(255, 255, 255, 0.08);
    margin-bottom: 0.5rem;
  }

  .nav-actions .btn,
  .nav-actions .lang-button {
    width: 100%;
    justify-content: center;
  }

  .navbar-container {
    flex-wrap: wrap;
    justify-content: space-between;
  }
}
</style>
