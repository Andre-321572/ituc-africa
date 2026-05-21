<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">Impact Mesurable</span>
        <h1 class="hero-sub__title">NOS PROJETS</h1>
        <p class="hero-sub__subtitle">
          Des initiatives concrètes et structurées pour répondre aux défis majeurs des travailleurs africains sur le long terme.
        </p>
      </div>
    </section>

    <!-- PROJECTS GRID -->
    <section class="section projects">
      <div class="container">
        <div class="projects-grid">
          <div v-for="project in projects" :key="project.title" class="project-card">
            <div class="project-card__status" :class="project.status">{{ project.statusText }}</div>
            <div class="project-card__content">
              <span class="project-id">{{ project.id }}</span>
              <h3>{{ project.title }}</h3>
              <p class="project-desc">{{ project.desc }}</p>
              
              <div class="project-meta">
                <div class="meta-item">
                  <strong>Objectif :</strong> {{ project.goal }}
                </div>
                <div class="meta-item">
                  <strong>Partenaires :</strong> {{ project.partners }}
                </div>
              </div>

              <div class="project-footer">
                <NuxtLink :to="project.link" class="btn-text">Détails du projet →</NuxtLink>
                <div class="project-tags">
                  <span v-for="tag in project.tags" :key="tag" class="p-tag">{{ tag }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- PROJECT MAP / STATS -->
    <section class="section project-stats">
      <div class="container">
        <div class="stats-banner">
          <div class="stat-box">
            <span class="number">12</span>
            <span class="label">Projets Actifs</span>
          </div>
          <div class="stat-box">
            <span class="number">45</span>
            <span class="label">Pays Couverts</span>
          </div>
          <div class="stat-box">
            <span class="number">200+</span>
            <span class="label">Points Focaux</span>
          </div>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<script setup>
const projects = [
  {
    id: 'ATUMNET',
    status: 'active',
    statusText: 'En cours',
    title: 'Réseau Syndical Africain sur la Migration',
    desc: 'ATUMNET est notre plateforme d\'action pour protéger les droits des travailleurs migrants et influencer les politiques migratoires continentales.',
    goal: 'Protection et défense des travailleurs migrants et de leurs familles.',
    partners: 'UA, OIT, Affiliés nationaux',
    tags: ['Migration', 'Droits'],
    link: '/nos-actions/projets/atumnet'
  },
  {
    id: 'ALREI',
    status: 'active',
    statusText: 'En cours',
    title: 'Institut Africain de Recherche et d\'Éducation',
    desc: 'L\'ALREI est le bras académique et de recherche de la CSI-Afrique, produisant des données et des formations de haut niveau.',
    goal: 'Produire des recherches ouvrières de qualité pour le plaidoyer.',
    partners: 'Universités, OIT, Centres de recherche',
    tags: ['Recherche', 'Éducation'],
    link: '/alrei'
  },
  {
    id: 'C190-ACTION',
    status: 'active',
    statusText: 'En cours',
    title: 'Projet d\'Appui à la Ratification C190',
    desc: 'Un projet ciblé pour accompagner les syndicats nationaux dans leur lobbying pour la ratification de la convention sur la violence et le harcèlement.',
    goal: 'Zéro violence dans le monde du travail en Afrique.',
    partners: 'SIDA, ACTRAV-OIT',
    tags: ['Genre', 'Droits'],
    link: '/nos-actions/campagnes'
  },
  {
    id: 'INFORMAL-FORM',
    status: 'planned',
    statusText: 'Planifié',
    title: 'Transition vers l\'Économie Formelle',
    desc: 'Initiative visant à organiser les travailleurs de l\'économie informelle et à faciliter leur transition vers des emplois protégés et décents.',
    goal: 'Formalisation et protection sociale pour les travailleurs vulnérables.',
    partners: 'Gouvernements, Affiliés',
    tags: ['Économie', 'Social'],
    link: '/nos-actions/projets/informel'
  }
]
</script>

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

.projects-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 3rem;
}

.project-card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 10px 40px rgba(0,0,0,0.05);
  position: relative;
  border-top: 5px solid var(--color-primary);
  transition: transform 0.3s ease;
}

.project-card:hover { transform: translateY(-10px); }

.project-card__status {
  position: absolute;
  top: 1.5rem;
  right: 1.5rem;
  padding: 0.3rem 1rem;
  border-radius: 50px;
  font-size: 0.75rem;
  font-weight: 900;
  text-transform: uppercase;
}

.project-card__status.active { background: #e6f4ea; color: #1e7e34; }
.project-card__status.planned { background: #fff4e5; color: #cc8400; }

.project-card__content {
  padding: 1.5rem;
}

.project-id {
  color: var(--color-primary);
  font-weight: 900;
  font-size: 0.9rem;
  display: block;
  margin-bottom: 0.5rem;
}

.project-card h3 {
  font-size: 1.2rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 1rem;
  line-height: 1.2;
}

.project-desc {
  color: #555;
  margin-bottom: 1.5rem;
  line-height: 1.6;
  font-size: 0.85rem;
}

.project-meta {
  background: var(--color-bg-light);
  padding: 0.75rem 1rem;
  border-radius: 8px;
  margin-bottom: 1.5rem;
}

.meta-item {
  margin-bottom: 0.4rem;
  font-size: 0.8rem;
  color: #444;
}

.meta-item strong { color: var(--color-secondary); }

.project-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-top: 1px solid #eee;
  padding-top: 1.5rem;
}

.p-tag {
  background: #eee;
  color: #666;
  padding: 0.2rem 0.6rem;
  border-radius: 4px;
  font-size: 0.7rem;
  font-weight: 800;
  margin-left: 0.5rem;
}

.stats-banner {
  background: var(--color-secondary);
  color: white;
  padding: 4rem;
  border-radius: 12px;
  display: flex;
  justify-content: space-around;
  text-align: center;
}

.stat-box .number { font-size: 3rem; font-weight: 900; color: var(--color-primary); display: block; }
.stat-box .label { font-weight: 700; text-transform: uppercase; letter-spacing: 1px; opacity: 0.8; }

@media (max-width: 1024px) {
  .projects-grid { grid-template-columns: 1fr; }
}

@media (max-width: 768px) {
  .project-card__content { padding: 2rem; }
  .stats-banner { flex-direction: column; gap: 3rem; }
}
</style>
