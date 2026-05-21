<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">Centre de Connaissances</span>
        <h1 class="hero-sub__title">DOCUMENTS & RAPPORTS</h1>
        <p class="hero-sub__subtitle">
          Accédez à nos publications officielles, recherches approfondies et documents de gouvernance.
        </p>
      </div>
    </section>

    <!-- SEARCH & FILTERS -->
    <section class="section docs-filter">
      <div class="container">
        <div class="search-box">
          <input type="text" placeholder="Rechercher un document (ex: Constitution, ZLECAF, Genre...)" class="search-input" />
          <button class="btn btn--primary">RECHERCHER</button>
        </div>
      </div>
    </section>

    <!-- DOCUMENTS LIBRARY -->
    <section class="section docs-library">
      <div class="container">
        <div v-for="cat in documentCategories" :key="cat.name" class="doc-category">
          <h2 class="doc-category__title">{{ cat.name }}</h2>
          <div class="doc-list">
            <div v-for="doc in cat.files" :key="doc.title" class="doc-item">
              <div class="doc-item__icon">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path><polyline points="14 2 14 8 20 8"></polyline><line x1="16" y1="13" x2="8" y2="13"></line><line x1="16" y1="17" x2="8" y2="17"></line><polyline points="10 9 9 9 8 9"></polyline></svg>
              </div>
              <div class="doc-item__info">
                <h3>{{ doc.title }}</h3>
                <p class="doc-meta">{{ doc.year }} • {{ doc.size }} • PDF</p>
              </div>
              <a :href="doc.url" class="btn btn--outline btn--sm">TÉLÉCHARGER</a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- REQUEST SECTION -->
    <section class="section request-doc">
      <div class="container text-center">
        <div class="request-box">
          <h2>VOUS NE TROUVEZ PAS CE QUE VOUS CHERCHEZ ?</h2>
          <p>Contactez notre département de communication pour toute demande de documentation spécifique.</p>
          <NuxtLink to="/contact" class="btn btn--secondary">NOUS ÉCRIRE</NuxtLink>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<script setup>
const documentCategories = [
  {
    name: 'Gouvernance & Constitution',
    files: [
      { title: 'Constitution de la CSI-Afrique (Version révisée)', year: '2023', size: '1.2 MB', url: '#' },
      { title: 'Règlement Intérieur du Secrétariat', year: '2022', size: '0.8 MB', url: '#' },
      { title: 'Rapport du 5ème Congrès Ordinaire', year: '2023', size: '4.5 MB', url: '#' }
    ]
  },
  {
    name: 'Recherches (ALREI)',
    files: [
      { title: 'Africa\'s Growth Paradox: Informality and Platform Economy', year: '2024', size: '2.4 MB', url: '#' },
      { title: 'Human Rights-Based Approach to Trade in Africa', year: '2024', size: '1.5 MB', url: '#' },
      { title: 'From Solidarity Struggles to Trade Opportunities', year: '2023', size: '3.1 MB', url: '#' }
    ]
  },
  {
    name: 'Positions & Briefings',
    files: [
      { title: 'Position Paper on Sovereign Debt New Deal', year: '2025', size: '0.9 MB', url: '#' },
      { title: 'Decent Work and Fair Trade: Policy Paper to G20', year: '2024', size: '1.1 MB', url: '#' },
      { title: 'Statement on Fiscal Sovereignty and Taxation', year: '2024', size: '0.7 MB', url: '#' }
    ]
  },
  {
    name: 'Objectifs de Développement (ODD)',
    files: [
      { title: 'Zimbabwe: A Trade Union Focus on the SDGs', year: '2024', size: '1.8 MB', url: '#' },
      { title: 'Uganda: A Trade Union Focus on the SDGs', year: '2024', size: '1.7 MB', url: '#' },
      { title: 'Nigeria: A Trade Union Focus on the SDGs', year: '2024', size: '1.9 MB', url: '#' }
    ]
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

.docs-filter {
  background: var(--color-bg-light);
  padding: 3rem 0;
}

.search-box {
  display: flex;
  max-width: 800px;
  margin: 0 auto;
  gap: 1rem;
}

.search-input {
  flex: 1;
  padding: 1rem 1.5rem;
  border: 2px solid #ddd;
  border-radius: 8px;
  font-size: 1rem;
  font-family: inherit;
}

.search-input:focus {
  border-color: var(--color-primary);
  outline: none;
}

.doc-category {
  margin-bottom: 5rem;
}

.doc-category__title {
  font-size: 1.8rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 2rem;
  border-left: 6px solid var(--color-primary);
  padding-left: 1.5rem;
}

.doc-list {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

.doc-item {
  display: grid;
  grid-template-columns: 50px 1fr auto;
  align-items: center;
  background: white;
  padding: 0.75rem 1rem;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.03);
  transition: all 0.3s ease;
  border: 1px solid #eee;
}

.doc-item:hover {
  transform: translateX(10px);
  border-color: var(--color-primary);
  box-shadow: 0 10px 20px rgba(0,0,0,0.05);
}

.doc-item__icon {
  color: var(--color-primary);
}

.doc-item__icon svg { width: 30px; height: 30px; }

.doc-item__info h3 {
  font-size: 0.95rem;
  font-weight: 700;
  color: var(--color-secondary);
  margin-bottom: 0.2rem;
}

.doc-meta {
  font-size: 0.75rem;
  color: #888;
  font-weight: 600;
}

.btn--sm { padding: 0.6rem 1.2rem; font-size: 0.8rem; }

.request-box {
  background: var(--color-secondary);
  color: white;
  padding: 4rem;
  border-radius: 12px;
}

.request-box h2 { font-size: 2rem; font-weight: 900; margin-bottom: 1rem; }
.request-box p { font-size: 1.1rem; margin-bottom: 2.5rem; opacity: 0.8; }

@media (max-width: 768px) {
  .search-box { flex-direction: column; }
  .doc-item { grid-template-columns: 1fr; text-align: center; gap: 1rem; }
  .doc-item__icon { margin: 0 auto; }
  .doc-item:hover { transform: translateY(-5px); }
  .request-box { padding: 2rem 1.5rem; }
}
</style>
