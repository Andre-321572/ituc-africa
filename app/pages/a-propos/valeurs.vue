<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">Principes Directeurs</span>
        <h1 class="hero-sub__title">VALEURS & OBJECTIFS</h1>
        <p class="hero-sub__subtitle">
          Le socle de notre engagement pour une Afrique plus juste, démocratique et prospère pour tous les travailleurs.
        </p>
      </div>
    </section>

    <!-- CORE VALUES -->
    <section class="section values">
      <div class="container">
        <h2 class="section-title text-center">NOS VALEURS FONDAMENTALES</h2>
        <div class="values-grid">
          <div v-for="value in coreValues" :key="value.title" class="value-card">
            <div class="value-card__icon" v-html="value.icon"></div>
            <h3>{{ value.title }}</h3>
            <p>{{ value.desc }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- STRATEGIC OBJECTIVES -->
    <section class="section objectives">
      <div class="container">
        <div class="objectives-header">
          <h2 class="section-title">OBJECTIFS STRATÉGIQUES</h2>
          <p class="section-subtitle">Notre feuille de route pour transformer les structures sociales et économiques du continent.</p>
        </div>

        <div class="objectives-list">
          <div v-for="(obj, index) in strategicObjectives" :key="obj.title" class="obj-item">
            <div class="obj-item__number">0{{ index + 1 }}</div>
            <div class="obj-item__content">
              <h3>{{ obj.title }}</h3>
              <p>{{ obj.desc }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- SLOGAN BANNER -->
    <section class="slogan-banner">
      <div class="container text-center">
        <div class="slogan-content">
          <h2 class="slogan-text">"UNIR ET FAIRE LA DIFFÉRENCE"</h2>
          <p class="slogan-sub">Le cri de ralliement de la CSI-Afrique pour la force collective.</p>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<script setup>
const coreValues = [
  {
    title: 'Solidarité',
    desc: 'Le pilier de notre lutte pour soutenir les travailleurs dans leurs combats et conduire des actions collectives.',
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M23 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path></svg>'
  },
  {
    title: 'Démocratie',
    desc: 'Garantir des processus démocratiques internes et plaider pour une gouvernance transparente dans la société.',
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg>'
  },
  {
    title: 'Indépendance',
    desc: 'Maintenir des syndicats libres et autonomes face aux pressions politiques ou forces anti-travailleurs.',
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2v20M2 12h20"></path></svg>'
  },
  {
    title: 'Unité',
    desc: 'Renforcer la cohésion syndicale aux niveaux national, sous-régional et continental pour un pouvoir collectif.',
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"></circle><path d="M12 8v8M8 12h8"></path></svg>'
  },
  {
    title: 'Équité',
    desc: 'Lutter pour la justice sociale, l\'élimination des discriminations et un partage équitable des richesses.',
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 3v18M5 8l14 8M5 16l14-8"></path></svg>'
  }
]

const strategicObjectives = [
  {
    title: 'Organisation et Mobilisation',
    desc: 'Élargir l\'adhésion syndicale et renforcer le pouvoir des travailleurs par une organisation de masse efficace.'
  },
  {
    title: 'Démocratie Interne Syndicale',
    desc: 'Assurer une gouvernance syndicale inclusive, participative et transparente pour refléter la voix de la base.'
  },
  {
    title: 'Défense des Droits des Travailleurs',
    desc: 'Protéger la liberté d\'association, le droit de négociation collective et lutter contre le rétrécissement de l\'espace civique.'
  },
  {
    title: 'Transformation Économique et Sociale',
    desc: 'Plaider pour des politiques de travail décent, la formalisation de l\'économie informelle et la justice économique.'
  },
  {
    title: 'Protection Sociale Universelle',
    desc: 'Garantir l\'accès à la sécurité sociale, aux soins de santé et à des conditions de vie dignes pour tous les Africains.'
  },
  {
    title: 'Transition Juste et Action Climatique',
    desc: 'Façonner l\'agenda de durabilité environnementale tout en protégeant les moyens de subsistance des travailleurs.'
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

.hero-sub__subtitle {
  font-size: 1.25rem;
  max-width: 700px;
  margin: 0 auto;
  opacity: 0.8;
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.value-card {
  background: white;
  padding: 1.5rem 1rem;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 10px 30px rgba(0,0,0,0.05);
  transition: transform 0.3s ease, border-color 0.3s ease;
  border: 1px solid transparent;
}

.value-card:hover {
  transform: translateY(-10px);
  border-color: var(--color-primary);
}

.value-card__icon {
  width: 60px;
  height: 60px;
  background: var(--color-bg-light);
  color: var(--color-primary);
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  margin: 0 auto 1.5rem;
}

.value-card__icon svg { width: 30px; height: 30px; }

.value-card h3 {
  font-size: 1rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 0.5rem;
  text-transform: uppercase;
}

.value-card p {
  color: #666;
  font-size: 0.85rem;
  line-height: 1.5;
}

.objectives {
  background: var(--color-bg-light);
}

.objectives-header {
  max-width: 800px;
  margin-bottom: 4rem;
}

.section-subtitle {
  font-size: 1.2rem;
  color: #555;
  margin-top: 1rem;
}

.objectives-list {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 3rem;
}

.obj-item {
  display: flex;
  gap: 2rem;
  background: white;
  padding: 1.25rem;
  border-radius: 8px;
  transition: box-shadow 0.3s ease;
}

.obj-item:hover {
  box-shadow: 0 15px 30px rgba(0,0,0,0.05);
}

.obj-item__number {
  font-size: 2.5rem;
  font-weight: 900;
  color: var(--color-primary);
  opacity: 0.3;
  line-height: 1;
}

.obj-item__content h3 {
  font-size: 1rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 0.5rem;
}

.obj-item__content p {
  color: #555;
  line-height: 1.6;
  font-size: 0.85rem;
}

.slogan-banner {
  background: var(--color-primary);
  color: white;
  padding: 6rem 0;
  position: relative;
  overflow: hidden;
}

.slogan-banner::after {
  content: '';
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background: url('https://www.transparenttextures.com/patterns/cubes.png');
  opacity: 0.1;
}

.slogan-text {
  font-size: 3.5rem;
  font-weight: 900;
  margin-bottom: 1rem;
  letter-spacing: 2px;
}

.slogan-sub {
  font-size: 1.5rem;
  font-weight: 400;
  opacity: 0.9;
}

@media (max-width: 1024px) {
  .objectives-list { grid-template-columns: 1fr; }
}

@media (max-width: 768px) {
  .slogan-text { font-size: 2rem; }
  .slogan-sub { font-size: 1.1rem; }
}
</style>
