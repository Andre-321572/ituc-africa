<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">À Propos</span>
        <h1 class="hero-sub__title">NOTRE ORGANISATION</h1>
        <p class="hero-sub__subtitle">
          Représenter, défendre et unir les travailleurs africains pour un avenir de justice sociale.
        </p>
      </div>
    </section>

    <!-- IDENTITY SECTION -->
    <section class="section about-intro">
      <div class="container about-grid">
        <div class="about-content">
          <h2 class="section-title">QUI SOMMES-NOUS ?</h2>
          <p class="about-text">
            L'Organisation Régionale Africaine de la Confédération Syndicale Internationale (CSI-Afrique) est une organisation syndicale panafricaine créée en novembre 2007 après la fusion de deux anciennes organisations syndicales régionales, à savoir l'ICFTU-Afro et l'OATUU.
          </p>
          <p class="about-text">
            La CSI-Afrique a son siège à Lomé, au Togo. Actuellement, elle compte 107 centres syndicaux affiliés dans 52 pays africains. La CSI-Afrique représente 18 millions de membres déclarés.
          </p>
          <div class="identity-cards">
            <div class="id-card">
              <span class="id-card__label">Nom complet</span>
              <strong class="id-card__value">CSI-Afrique / ITUC-Africa</strong>
            </div>
            <div class="id-card">
              <span class="id-card__label">Slogan</span>
              <strong class="id-card__value">"Créer un monde meilleur pour les travailleurs en Afrique et au-delà"</strong>
            </div>
          </div>
        </div>
        <div class="about-image">
          <img src="https://ituc-africa.org/IMG/logo/siteon0.jpg" alt="CSI-Afrique Logo Large" class="about-logo-large" />
        </div>
      </div>
    </section>

    <!-- MISSION & VISION -->
    <section class="section mission-vision">
      <div class="container">
        <div class="mission-grid">
          <div class="mission-card">
            <div class="mission-icon">🎯</div>
            <h3>NOTRE MISSION</h3>
            <p>Représenter les travailleurs en Afrique à travers l'unité, le plaidoyer et le renforcement des capacités pour le travail décent et la justice sociale.</p>
          </div>
          <div class="mission-card">
            <div class="mission-icon">👁️</div>
            <h3>NOTRE VISION</h3>
            <p>Une Afrique où tous les travailleurs jouissent de leurs droits fondamentaux, travaillent dans la dignité et bénéficient d'une protection sociale universelle.</p>
          </div>
          <div class="mission-card">
            <div class="mission-icon">🤝</div>
            <h3>NOS VALEURS</h3>
            <p>Solidarité, Démocratie, Unité, Équité et Indépendance syndicale sont les piliers de toutes nos actions sur le continent.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- HISTORY / FUSION -->
    <section class="section history">
      <div class="container">
        <div class="history-inner">
          <h2 class="section-title text-center">NOTRE HISTOIRE</h2>
          <div class="timeline">
            <div class="timeline-item">
              <div class="timeline-date">NOV 2007</div>
              <div class="timeline-content">
                <h4>LA FUSION HISTORIQUE</h4>
                <p>Création de la CSI-Afrique à Accra, Ghana, issue de la fusion de l'ICFTU-Afro et de l'OATUU, marquant une nouvelle ère pour l'unité syndicale africaine.</p>
              </div>
            </div>
            <div class="timeline-item">
              <div class="timeline-date">SIÈGE</div>
              <div class="timeline-content">
                <h4>ANCRAGE À LOMÉ</h4>
                <p>Établissement du siège permanent à Lomé, Togo, au Centre FOPADESC, point névralgique de la coordination syndicale continentale.</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- LEADERSHIP (JOEL ODIGIE) -->
    <section class="section leadership">
      <div class="container">
        <h2 class="section-title text-center">NOTRE LEADERSHIP</h2>
        <div class="sg-profile">
          <div class="sg-image">
             <img src="https://ituc-africa.org/IMG/logo/sg2-csi.jpg" alt="Joel Akhator Odigie" />
          </div>
          <div class="sg-info">
            <h3>JOEL AKHATOR ODIGIE</h3>
            <span class="badge badge--primary">Secrétaire Général</span>
            <p class="sg-bio">
              Élu lors du 5ème Congrès Ordinaire, Joel Akhator Odigie dirige l'organisation avec une vision axée sur la transformation structurelle de l'Afrique et le renforcement du pouvoir des travailleurs face aux défis mondiaux.
            </p>
            <NuxtLink to="/a-propos/secretariat" class="link-voir-tout">Découvrir le Secrétariat ↗</NuxtLink>
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

.about-grid {
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  gap: 4rem;
  align-items: center;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 2rem;
}

.about-text {
  font-size: 1.1rem;
  margin-bottom: 1.5rem;
  color: #444;
}

.identity-cards {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.5rem;
  margin-top: 2rem;
}

.id-card {
  background: var(--color-bg-light);
  padding: 1.5rem;
  border-left: 5px solid var(--color-primary);
  border-radius: 4px;
}

.id-card__label {
  display: block;
  font-size: 0.8rem;
  font-weight: 800;
  text-transform: uppercase;
  color: var(--color-primary);
  margin-bottom: 0.5rem;
}

.id-card__value {
  font-size: 1.2rem;
  color: var(--color-secondary);
}

.about-logo-large {
  width: 100%;
  max-width: 300px;
  margin: 0 auto;
  filter: drop-shadow(0 10px 20px rgba(0,0,0,0.1));
}

.mission-vision {
  background: var(--color-bg-light);
}

.mission-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.mission-card {
  background: white;
  padding: 3rem 2rem;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 10px 30px rgba(0,0,0,0.05);
  transition: transform 0.3s ease;
}

.mission-card:hover { transform: translateY(-10px); }

.mission-icon { font-size: 3rem; margin-bottom: 1.5rem; }

.mission-card h3 {
  font-weight: 900;
  color: var(--color-primary);
  margin-bottom: 1rem;
}

.timeline {
  max-width: 800px;
  margin: 4rem auto 0;
  position: relative;
}

.timeline::before {
  content: '';
  position: absolute;
  top: 0;
  bottom: 0;
  left: 50%;
  width: 2px;
  background: var(--color-bg-light);
  transform: translateX(-50%);
}

.timeline-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  margin-bottom: 3rem;
}

.timeline-date {
  width: 45%;
  text-align: right;
  font-weight: 900;
  color: var(--color-primary);
  font-size: 1.5rem;
}

.timeline-content {
  width: 45%;
  background: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.05);
}

.timeline-content h4 { font-weight: 800; color: var(--color-secondary); margin-bottom: 0.5rem; }

.sg-profile {
  display: grid;
  grid-template-columns: 300px 1fr;
  gap: 3rem;
  background: white;
  padding: 3rem;
  border-radius: 12px;
  box-shadow: 0 15px 40px rgba(0,0,0,0.05);
  margin-top: 3rem;
  align-items: center;
}

.sg-image img {
  width: 100%;
  border-radius: 8px;
  border-bottom: 8px solid var(--color-primary);
}

.sg-info h3 { font-size: 2rem; font-weight: 900; color: var(--color-secondary); margin-bottom: 0.5rem; }
.sg-bio { font-size: 1.1rem; color: #555; line-height: 1.6; margin: 1.5rem 0; }

@media (max-width: 1024px) {
  .about-grid, .mission-grid, .sg-profile { grid-template-columns: 1fr; text-align: center; }
  .timeline::before { left: 0; }
  .timeline-date, .timeline-content { width: 100%; text-align: left; }
  .timeline-date { margin-bottom: 1rem; }
}
</style>
