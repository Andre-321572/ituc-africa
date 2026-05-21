<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub hero-alrei">
      <div class="container">
        <span class="badge badge--white">Recherche & Éducation</span>
        <h1 class="hero-sub__title">ALREI</h1>
        <p class="hero-sub__subtitle">
          Africa Labour Research and Education Institute : le bras académique et stratégique du mouvement syndical africain.
        </p>
      </div>
    </section>

    <!-- INTRODUCTION -->
    <section class="section alrei-intro">
      <div class="container grid-2">
        <div class="alrei-text">
          <h2 class="section-title">NOTRE MISSION</h2>
          <p class="lead">L'ALREI a été créé pour combler le besoin de compétences techniques et de capacités de recherche au sein des mouvements syndicaux africains.</p>
          <p>Notre objectif est de fournir aux syndicats les données et les connaissances nécessaires pour influencer efficacement les politiques économiques et sociales aux niveaux national et continental.</p>
          <div class="alrei-stats">
            <div class="a-stat">
              <span class="num">15+</span>
              <span class="lab">Années d'expertise</span>
            </div>
            <div class="a-stat">
              <span class="num">500+</span>
              <span class="lab">Cadres formés / an</span>
            </div>
          </div>
        </div>
        <div class="alrei-image">
           <img src="/images/news_women_rights.png" alt="Formation ALREI" class="img-round" />
        </div>
      </div>
    </section>

    <!-- PILLARS -->
    <section class="section alrei-pillars">
      <div class="container">
        <h2 class="section-title text-center">NOS DOMAINES D'INTERVENTION</h2>
        <div class="pillars-grid">
          <div v-for="pillar in pillars" :key="pillar.title" class="pillar-card">
            <div class="pillar-icon" v-html="pillar.icon"></div>
            <h3>{{ pillar.title }}</h3>
            <p>{{ pillar.desc }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- FLAGSHIP EVENT: NEW YEAR SCHOOL -->
    <section class="section nys">
      <div class="container">
        <div class="nys-box">
          <div class="nys-content">
            <span class="nys-tag">Événement Phare</span>
            <h2>NEW YEAR SCHOOL (NYS)</h2>
            <p>Le rendez-vous annuel incontournable où syndicalistes, universitaires et décideurs se réunissent pour réfléchir aux enjeux socio-économiques contemporains et formuler des stratégies communes.</p>
            <ul class="nys-list">
              <li>Débats de haut niveau</li>
              <li>Ateliers de prospective</li>
              <li>Réseautage académique</li>
            </ul>
            <button class="btn btn--primary">DÉCOUVRIR L'ÉDITION 2025</button>
          </div>
          <div class="nys-image">
            <img src="/images/news_peace_justice.png" alt="New Year School" />
          </div>
        </div>
      </div>
    </section>

    <!-- RESEARCH HIGHLIGHTS -->
    <section class="section alrei-research">
      <div class="container">
        <h2 class="section-title">DERNIÈRES RECHERCHES</h2>
        <div class="research-grid">
          <div v-for="res in research" :key="res.title" class="res-card">
            <span class="res-tag">{{ res.tag }}</span>
            <h3>{{ res.title }}</h3>
            <p>{{ res.excerpt }}</p>
            <NuxtLink to="/ressources/documents" class="btn-text">Lire le rapport →</NuxtLink>
          </div>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<script setup>
const pillars = [
  {
    title: 'Recherche Politique',
    desc: 'Coordination de projets de recherche régionaux sur la ZLECAF, la dette et les transformations structurelles.',
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>'
  },
  {
    title: 'Éducation Ouvrière',
    desc: 'Développement de modules de formation pour les leaders syndicaux sur la négociation et le plaidoyer.',
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 10v6M2 10l10-5 10 5-10 5z"></path><path d="M6 12v5c3 3 9 3 12 0v-5"></path></svg>'
  },
  {
    title: 'Veille Économique',
    desc: 'Analyse des tendances du marché du travail, de l\'économie informelle et de la protection sociale.',
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="18" y1="20" x2="18" y2="10"></line><line x1="12" y1="20" x2="12" y2="4"></line><line x1="6" y1="20" x2="6" y2="14"></line></svg>'
  }
]

const research = [
  {
    tag: 'Économie',
    title: 'Le Paradoxe de la Croissance en Afrique',
    excerpt: 'Une étude sur la croissance sans emploi et la montée de l\'économie de plateforme sur le continent.'
  },
  {
    tag: 'Commerce',
    title: 'ZLECAF et Droits Humains',
    excerpt: 'Analyse des risques et opportunités du commerce continental pour les standards du travail.'
  },
  {
    tag: 'Social',
    title: 'L\'avenir de la Protection Sociale',
    excerpt: 'Recherche sur l\'extension de la couverture aux travailleurs du secteur informel.'
  }
]
</script>

<style scoped>
.hero-alrei {
  background: linear-gradient(rgba(27, 61, 27, 0.9), rgba(27, 61, 27, 0.9)), url('https://www.transparenttextures.com/patterns/clean-gray-paper.png');
  color: white;
}

.grid-2 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.lead {
  font-size: 1.4rem;
  font-weight: 700;
  color: var(--color-secondary);
  margin-bottom: 1.5rem;
}

.alrei-stats {
  display: flex;
  gap: 3rem;
  margin-top: 3rem;
}

.a-stat .num {
  font-size: 2.5rem;
  font-weight: 900;
  color: var(--color-primary);
  display: block;
}

.a-stat .lab {
  font-weight: 800;
  text-transform: uppercase;
  font-size: 0.8rem;
  color: #777;
}

.img-round {
  border-radius: 20px;
  box-shadow: 0 20px 40px rgba(0,0,0,0.1);
}

.alrei-pillars {
  background: var(--color-bg-light);
}

.pillars-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2.5rem;
}

.pillar-card {
  background: white;
  padding: 1.5rem 1rem;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 10px 30px rgba(0,0,0,0.05);
}

.pillar-icon {
  color: var(--color-primary);
  margin-bottom: 1.5rem;
}

.pillar-icon svg { width: 40px; height: 40px; }

.pillar-card h3 {
  font-size: 1rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 0.5rem;
}

.nys-box {
  background: var(--color-secondary);
  color: white;
  border-radius: 20px;
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  overflow: hidden;
  box-shadow: 0 20px 60px rgba(0,0,0,0.15);
}

.nys-content {
  padding: 4rem;
}

.nys-tag {
  background: var(--color-primary);
  padding: 0.3rem 0.8rem;
  font-size: 0.75rem;
  font-weight: 900;
  border-radius: 4px;
  margin-bottom: 1.5rem;
  display: inline-block;
}

.nys-content h2 { font-size: 2.5rem; font-weight: 900; margin-bottom: 1.5rem; }
.nys-content p { font-size: 1.1rem; opacity: 0.9; line-height: 1.6; margin-bottom: 2rem; }

.nys-list {
  list-style: none;
  padding: 0;
  margin-bottom: 2.5rem;
}

.nys-list li {
  margin-bottom: 0.8rem;
  padding-left: 1.5rem;
  position: relative;
  font-weight: 700;
}

.nys-list li::before {
  content: '★';
  color: var(--color-primary);
  position: absolute;
  left: 0;
}

.nys-image img { width: 100%; height: 100%; object-fit: cover; }

.research-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.res-card {
  padding: 1.25rem;
  border: 1px solid #eee;
  border-radius: 12px;
  transition: all 0.3s ease;
}

.res-card:hover { border-color: var(--color-primary); box-shadow: 0 10px 20px rgba(0,0,0,0.05); }

.res-tag {
  color: var(--color-primary);
  font-weight: 900;
  font-size: 0.75rem;
  text-transform: uppercase;
  margin-bottom: 1rem;
  display: block;
}

.res-card h3 { font-size: 1rem; font-weight: 800; color: var(--color-secondary); margin-bottom: 0.5rem; line-height: 1.3; }
.res-card p { color: #666; font-size: 0.85rem; margin-bottom: 1rem; }

@media (max-width: 1024px) {
  .grid-2, .nys-box, .pillars-grid, .research-grid { grid-template-columns: 1fr; }
  .nys-image { height: 300px; order: -1; }
  .nys-content { padding: 2rem; }
}
</style>
