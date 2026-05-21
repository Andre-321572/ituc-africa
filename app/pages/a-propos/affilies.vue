<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">Réseau Continental</span>
        <h1 class="hero-sub__title">NOS AFFILIÉS</h1>
        <p class="hero-sub__subtitle">
          Unissant plus de 100 organisations syndicales nationales à travers 52 pays pour porter la voix des travailleurs africains.
        </p>
      </div>
    </section>

    <!-- KEY FIGURES -->
    <section class="section stats-affilies">
      <div class="container">
        <div class="stats-grid">
          <div class="stat-item">
            <div class="stat-value">107</div>
            <div class="stat-label">Organisations Affiliées</div>
          </div>
          <div class="stat-item">
            <div class="stat-value">52</div>
            <div class="stat-label">Pays Africains</div>
          </div>
          <div class="stat-item">
            <div class="stat-value">18M</div>
            <div class="stat-label">Travailleurs Représentés</div>
          </div>
        </div>
      </div>
    </section>

    <!-- REGIONAL DIRECTORY -->
    <section class="section regions">
      <div class="container">
        <h2 class="section-title text-center">RÉPARTITION PAR RÉGION</h2>
        
        <div class="regions-tabs">
          <button 
            v-for="region in regions" 
            :key="region.id"
            @click="activeRegion = region.id"
            :class="['region-tab', { active: activeRegion === region.id }]"
          >
            {{ region.name }}
          </button>
        </div>

        <div class="region-content">
          <div class="region-card" v-if="currentRegion">
            <h3 class="region-card__title">{{ currentRegion.name }}</h3>
            <div class="affiliates-grid">
              <div v-for="country in currentRegion.countries" :key="country.name" class="country-group">
                <h4 class="country-name">{{ country.name }}</h4>
                <ul class="affiliates-list">
                  <li v-for="org in country.orgs" :key="org">{{ org }}</li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- JOIN SECTION -->
    <section class="section join-network">
      <div class="container text-center">
        <div class="join-box">
          <h2>REJOINDRE LE RÉSEAU</h2>
          <p>Vous êtes une organisation syndicale nationale et souhaitez rejoindre la CSI-Afrique ?</p>
          <NuxtLink to="/contact" class="btn btn--primary">DEMANDER L'AFFILIATION</NuxtLink>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<script setup>
const activeRegion = ref('west')

const regions = [
  {
    id: 'west',
    name: 'Afrique de l\'Ouest',
    countries: [
      { name: 'Togo', orgs: ['CSTT', 'UNSIT', 'CNTT', 'UGSL'] },
      { name: 'Côte d\'Ivoire', orgs: ['DIGNITE', 'UGTCI', 'FESACI'] },
      { name: 'Sénégal', orgs: ['CNTS', 'UNSAS', 'CSA'] },
      { name: 'Nigéria', orgs: ['NLC (Nigeria Labour Congress)'] },
      { name: 'Ghana', orgs: ['TUC (Trades Union Congress)'] }
    ]
  },
  {
    id: 'north',
    name: 'Afrique du Nord',
    countries: [
      { name: 'Maroc', orgs: ['CDT', 'UGTM', 'UMT'] },
      { name: 'Tunisie', orgs: ['UGTT'] },
      { name: 'Algérie', orgs: ['UGTA'] },
      { name: 'Égypte', orgs: ['EFITU'] }
    ]
  },
  {
    id: 'central',
    name: 'Afrique Centrale',
    countries: [
      { name: 'Centrafrique', orgs: ['CSTC', 'USTC', 'CNTC'] },
      { name: 'Cameroun', orgs: ['CSTC', 'GTC'] },
      { name: 'Gabon', orgs: ['COSYGA', 'CGSL'] },
      { name: 'RD Congo', orgs: ['UNTC', 'CSC'] }
    ]
  },
  {
    id: 'east',
    name: 'Afrique de l\'Est',
    countries: [
      { name: 'Madagascar', orgs: ['FI.SE.MA', 'SEKRIMA', 'USAM', 'FISEMARE'] },
      { name: 'Kenya', orgs: ['COTU (K)'] },
      { name: 'Ouganda', orgs: ['NOTU'] },
      { name: 'Éthiopie', orgs: ['CETU'] }
    ]
  },
  {
    id: 'south',
    name: 'Afrique Australe',
    countries: [
      { name: 'Afrique du Sud', orgs: ['COSATU', 'FEDUSA', 'NACTU'] },
      { name: 'Angola', orgs: ['CGSILA', 'UNTA-CS'] },
      { name: 'Botswana', orgs: ['BFTU'] },
      { name: 'Malawi', orgs: ['MCTU'] },
      { name: 'Zimbabwe', orgs: ['ZCTU'] }
    ]
  }
]

const currentRegion = computed(() => regions.find(r => r.id === activeRegion.value))
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

.hero-sub__subtitle {
  font-size: 1.25rem;
  max-width: 700px;
  margin: 0 auto;
  opacity: 0.8;
}

.stats-affilies {
  background: var(--color-bg-light);
  padding: 4rem 0;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  text-align: center;
}

.stat-value {
  font-size: 3rem;
  font-weight: 900;
  color: var(--color-primary);
  margin-bottom: 0.5rem;
}

.stat-label {
  font-weight: 800;
  text-transform: uppercase;
  color: var(--color-secondary);
  font-size: 0.9rem;
  letter-spacing: 1px;
}

.regions-tabs {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 3rem;
  flex-wrap: wrap;
}

.region-tab {
  padding: 1rem 2rem;
  border: 2px solid var(--color-secondary);
  background: transparent;
  color: var(--color-secondary);
  font-weight: 800;
  cursor: pointer;
  transition: all 0.3s ease;
  border-radius: 50px;
  text-transform: uppercase;
  font-size: 0.8rem;
}

.region-tab.active, .region-tab:hover {
  background: var(--color-secondary);
  color: white;
}

.region-card {
  background: white;
  padding: 1.5rem;
  border-radius: 12px;
  box-shadow: 0 15px 40px rgba(0,0,0,0.05);
}

.region-card__title {
  font-size: 1.2rem;
  font-weight: 900;
  color: var(--color-primary);
  margin-bottom: 1.5rem;
  text-align: center;
  text-transform: uppercase;
}

.affiliates-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 3rem;
}

.country-name {
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 1rem;
  padding-bottom: 0.3rem;
  border-bottom: 2px solid var(--color-primary);
  display: inline-block;
  font-size: 0.9rem;
}

.affiliates-list {
  list-style: none;
  padding: 0;
}

.affiliates-list li {
  margin-bottom: 0.4rem;
  color: #555;
  font-weight: 600;
  position: relative;
  padding-left: 1.2rem;
  font-size: 0.85rem;
}

.affiliates-list li::before {
  content: '•';
  color: var(--color-primary);
  position: absolute;
  left: 0;
  font-weight: 900;
}

.join-box {
  background: var(--color-secondary);
  color: white;
  padding: 2rem;
  border-radius: 12px;
}

.join-box h2 {
  font-size: 2.5rem;
  font-weight: 900;
  margin-bottom: 1rem;
}

.join-box p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  opacity: 0.9;
}

@media (max-width: 768px) {
  .stats-grid { grid-template-columns: 1fr; }
  .region-card { padding: 2rem 1.5rem; }
  .join-box { padding: 2rem 1rem; }
}
</style>
