<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub hero-campagnes">
      <div class="container">
        <span class="badge badge--white">Agir pour le Changement</span>
        <h1 class="hero-sub__title">NOS CAMPAGNES</h1>
        <p class="hero-sub__subtitle">
          De la ratification de la C190 à la justice climatique, nous menons des luttes stratégiques pour transformer la vie des travailleurs.
        </p>
      </div>
    </section>

    <!-- MAIN CAMPAIGNS -->
    <section class="section campaigns">
      <div class="container">
        <div v-for="(camp, index) in campaigns" :key="camp.title" :class="['campaign-block', { 'reverse': index % 2 !== 0 }]">
          <div class="campaign-block__content">
            <span class="campaign-tag">{{ camp.tag }}</span>
            <h2>{{ camp.title }}</h2>
            <p class="campaign-desc">{{ camp.desc }}</p>
            <div class="campaign-highlights">
              <div v-for="h in camp.highlights" :key="h" class="h-item">
                <span class="h-check">✓</span> {{ h }}
              </div>
            </div>
            <button class="btn btn--secondary">EN SAVOIR PLUS SUR CETTE LUTTE</button>
          </div>
          <div class="campaign-block__image">
             <div class="img-placeholder" :style="{ backgroundColor: camp.color }">
               <div class="placeholder-text">{{ camp.shortTitle }}</div>
             </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CALL TO ACTION -->
    <section class="section cta-campagne">
      <div class="container text-center">
        <div class="cta-inner">
          <h2>SOUTENEZ NOS ACTIONS</h2>
          <p>Rejoignez le mouvement et aidez-nous à faire pression pour une Afrique plus juste.</p>
          <div class="cta-btns">
            <NuxtLink to="/ressources/documents" class="btn btn--primary">LIRE LES DÉCLARATIONS</NuxtLink>
            <NuxtLink to="/contact" class="btn btn--outline">NOUS CONTACTER</NuxtLink>
          </div>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<script setup>
const campaigns = [
  {
    tag: 'Droits Humains',
    title: 'Ratification de la Convention 190 (OIT)',
    shortTitle: 'STOP HARCÈLEMENT',
    desc: 'Notre campagne phare pour éliminer la violence et le harcèlement dans le monde du travail. Nous poussons les gouvernements africains à ratifier et implémenter ce standard international crucial.',
    color: '#DA532C',
    highlights: [
      'Protection contre le harcèlement sexuel',
      'Sécurité pour tous les types de travailleurs',
      'Inclusion dans les conventions collectives',
      'Zéro tolérance sur le lieu de travail'
    ]
  },
  {
    tag: 'Justice Économique',
    title: 'Annulation de la Dette & Justice Fiscale',
    shortTitle: 'STOP THE BLEEDING',
    desc: 'Lutter contre le fardeau de la dette souveraine qui paralyse les budgets sociaux en Afrique. Nous exigeons un nouveau pacte pour le développement et l\'arrêt des flux financiers illicites.',
    color: '#1B3D1B',
    highlights: [
      'Annulation des dettes insoutenables',
      'Lutte contre l\'évasion fiscale',
      'Financement des services publics',
      'Transparence des emprunts souverains'
    ]
  },
  {
    tag: 'Protection Sociale',
    title: 'Protection Sociale pour Tous & Migrants',
    shortTitle: 'SÉCURITÉ SOCIALE',
    desc: 'Garantir que chaque travailleur, y compris les migrants et ceux de l\'économie informelle, bénéficie d\'une couverture santé et d\'une retraite digne.',
    color: '#C8923A',
    highlights: [
      'Portabilité des droits pour les migrants',
      'Extension à l\'économie informelle',
      'Ratification du protocole de libre circulation',
      'Digitalisation de la protection sociale'
    ]
  },
  {
    tag: 'Environnement',
    title: 'Transition Juste & Justice Climatique',
    shortTitle: 'JUST TRANSITION',
    desc: 'Assurer que la transition vers une économie verte ne se fasse pas au détriment des travailleurs africains. Nous militons pour des emplois verts décents et durables.',
    color: '#2a5a2a',
    highlights: [
      'Protection des emplois dans l\'énergie',
      'Reconversion et formation technique',
      'Financement climatique sous forme de dons',
      'Participation aux tables de décision COP'
    ]
  }
]
</script>

<style scoped>
.hero-campagnes {
  background: linear-gradient(rgba(218, 83, 44, 0.9), rgba(27, 61, 27, 0.9)), url('https://www.transparenttextures.com/patterns/asfalt-dark.png');
  color: white;
}

.badge--white {
  background: white;
  color: var(--color-primary);
  font-weight: 800;
  padding: 0.4rem 1rem;
  border-radius: 50px;
  text-transform: uppercase;
  font-size: 0.8rem;
}

.campaign-block {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5rem;
  align-items: center;
  margin-bottom: 4rem;
}

.campaign-block.reverse {
  direction: rtl;
}

.campaign-block.reverse .campaign-block__content {
  direction: ltr;
}

.campaign-tag {
  color: var(--color-primary);
  font-weight: 900;
  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: 0.85rem;
  display: block;
  margin-bottom: 1rem;
}

.campaign-block__content h2 {
  font-size: 1.5rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 1rem;
  line-height: 1.1;
}

.campaign-desc {
  font-size: 0.9rem;
  color: #444;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.campaign-highlights {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin-bottom: 2.5rem;
}

.h-item {
  font-weight: 700;
  color: var(--color-secondary);
  display: flex;
  align-items: center;
  gap: 0.8rem;
  font-size: 0.85rem;
}

.h-check {
  color: var(--color-primary);
  font-weight: 900;
}

.campaign-block__image {
  height: 200px;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0,0,0,0.1);
}

.img-placeholder {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.placeholder-text {
  color: white;
  font-size: 3rem;
  font-weight: 900;
  text-align: center;
  padding: 2rem;
  opacity: 0.4;
  transform: rotate(-15deg);
}

.cta-campagne {
  background: var(--color-bg-light);
}

.cta-inner {
  max-width: 800px;
  margin: 0 auto;
}

.cta-inner h2 { font-size: 2.5rem; font-weight: 900; color: var(--color-secondary); margin-bottom: 1rem; }
.cta-inner p { font-size: 1.2rem; color: #555; margin-bottom: 2.5rem; }

.cta-btns {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
}

.btn--outline {
  border: 2px solid var(--color-primary);
  color: var(--color-primary);
  background: transparent;
}

.btn--outline:hover {
  background: var(--color-primary);
  color: white;
}

@media (max-width: 1024px) {
  .campaign-block { grid-template-columns: 1fr; gap: 3rem; margin-bottom: 5rem; }
  .campaign-block.reverse { direction: ltr; }
  .campaign-block__image { height: 300px; order: -1; }
  .campaign-highlights { grid-template-columns: 1fr; }
}
</style>
