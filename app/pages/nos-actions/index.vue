<template>
  <div class="site">
    <TheNavbar />

    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">Impact & Action</span>
        <h1 class="hero-sub__title">NOS ACTIONS</h1>
        <p class="hero-sub__subtitle">
          Découvrez comment la CSI-Afrique transforme le paysage syndical et social du continent à travers ses programmes et campagnes.
        </p>
      </div>
    </section>

    <section class="section actions-hub">
      <div class="container">
        <div class="hub-grid">
          <NuxtLink to="/nos-actions/activites" class="hub-card">
            <div class="hub-card__icon">📅</div>
            <h3>ACTIVITÉS</h3>
            <p>Découvrez nos derniers événements, réunions statutaires et écoles syndicales à travers le continent.</p>
            <span class="hub-card__link">Voir les activités →</span>
          </NuxtLink>

          <NuxtLink to="/nos-actions/programmes" class="hub-card">
            <div class="hub-card__icon">📊</div>
            <h3>PROGRAMMES</h3>
            <p>Nos domaines d'intervention stratégiques pour le développement durable et le travail décent en Afrique.</p>
            <span class="hub-card__link">Explorer les programmes →</span>
          </NuxtLink>

          <NuxtLink to="/nos-actions/campagnes" class="hub-card">
            <div class="hub-card__icon">📢</div>
            <h3>CAMPAGNES</h3>
            <p>Nos initiatives de plaidoyer mondial et continental pour la justice sociale et les droits des travailleurs.</p>
            <span class="hub-card__link">Rejoindre nos campagnes →</span>
          </NuxtLink>

          <NuxtLink to="/nos-actions/projets" class="hub-card">
            <div class="hub-card__icon">🏗️</div>
            <h3>PROJETS</h3>
            <p>Actions concrètes de renforcement des capacités et de soutien technique à nos affiliés.</p>
            <span class="hub-card__link">Découvrir les projets →</span>
          </NuxtLink>
        </div>
      </div>
    </section>

    <!-- HIGHLIGHT SECTION: ALREI -->
    <section class="section alrei-highlight">
      <div class="container">
        <div class="alrei-box">
          <div class="alrei-content">
            <span class="badge badge--primary">Focus</span>
            <h2>ALREI - African Labour Research and Education Institute</h2>
            <p>L'ALREI est le bras de recherche et d'éducation de la CSI-Afrique, dédié à la production de connaissances et au renforcement des capacités syndicales.</p>
            <NuxtLink to="/alrei" class="btn btn--primary">Accéder à ALREI</NuxtLink>
          </div>
          <div class="alrei-visual">
            <div class="abstract-shape"></div>
          </div>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<style scoped>
.hero-sub {
  background-color: var(--color-secondary);
  color: var(--color-white);
  padding: 6rem 0;
  text-align: center;
}

.hero-sub__title {
  font-size: 3.5rem;
  font-weight: 900;
  margin-bottom: 1rem;
}

.hero-sub__subtitle {
  font-size: 1.25rem;
  max-width: 700px;
  margin: 0 auto;
  opacity: 0.8;
}

.hub-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 2rem;
  margin-top: -3rem;
}

.hub-card {
  background: white;
  padding: 3rem;
  border-radius: 12px;
  box-shadow: 0 15px 40px rgba(0,0,0,0.1);
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
  border-bottom: 5px solid transparent;
}

.hub-card:hover {
  transform: translateY(-10px);
  border-color: var(--color-primary);
}

.hub-card__icon {
  font-size: 3rem;
  margin-bottom: 1.5rem;
}

.hub-card h3 {
  font-weight: 900;
  color: var(--color-secondary);
  font-size: 1.8rem;
  margin-bottom: 1rem;
}

.hub-card p {
  color: #666;
  font-size: 1.1rem;
  line-height: 1.6;
  margin-bottom: 2rem;
  flex-grow: 1;
}

.hub-card__link {
  font-weight: 800;
  color: var(--color-primary);
  text-transform: uppercase;
  font-size: 0.9rem;
}

.alrei-box {
  background: var(--color-bg-light);
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  border-radius: 12px;
  overflow: hidden;
  align-items: center;
}

.alrei-content {
  padding: 4rem;
}

.alrei-content h2 {
  font-size: 2.5rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin: 1.5rem 0;
}

.alrei-content p {
  font-size: 1.2rem;
  color: #444;
  margin-bottom: 2rem;
}

.alrei-visual {
  height: 100%;
  background: var(--color-tertiary);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  min-height: 300px;
}

.abstract-shape {
  width: 150px;
  height: 150px;
  background: rgba(255,255,255,0.2);
  border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
  animation: morph 8s ease-in-out infinite;
}

@keyframes morph {
  0%, 100% { border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%; }
  50% { border-radius: 70% 30% 30% 70% / 70% 70% 30% 30%; }
}

@media (max-width: 768px) {
  .hub-grid, .alrei-box { grid-template-columns: 1fr; }
  .hub-card { padding: 2rem; }
  .alrei-content { padding: 2rem; }
}
</style>
