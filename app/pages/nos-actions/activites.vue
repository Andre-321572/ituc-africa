<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">Au Cœur du Terrain</span>
        <h1 class="hero-sub__title">NOS ACTIVITÉS</h1>
        <p class="hero-sub__subtitle">
          Mobilisation, formation et plaidoyer : découvrez comment nous agissons quotidiennement pour les travailleurs africains.
        </p>
      </div>
    </section>

    <!-- ACTIVITY CATEGORIES -->
    <section class="section categories">
      <div class="container">
        <div class="category-grid">
          <div v-for="cat in categories" :key="cat.title" class="cat-card">
            <div class="cat-card__img-wrapper">
              <img :src="cat.image" :alt="cat.title" class="cat-card__img" />
              <div class="cat-card__icon" v-html="cat.icon"></div>
            </div>
            <div class="cat-card__content">
              <h3>{{ cat.title }}</h3>
              <p>{{ cat.desc }}</p>
              <ul class="cat-list">
                <li v-for="item in cat.items" :key="item">{{ item }}</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CALENDAR / RECENT EVENTS -->
    <section class="section recent-activities">
      <div class="container">
        <h2 class="section-title">ACTIVITÉS RÉCENTES & À VENIR</h2>
        <div class="activity-timeline">
          <div v-for="event in recentEvents" :key="event.title" class="event-item">
            <div class="event-date">
              <span class="day">{{ event.day }}</span>
              <span class="month">{{ event.month }}</span>
            </div>
            <div class="event-info">
              <span class="event-tag">{{ event.tag }}</span>
              <h3>{{ event.title }}</h3>
              <p><i class="icon-loc">📍</i> {{ event.location }}</p>
              <p class="event-desc">{{ event.desc }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<script setup>
const categories = [
  {
    title: 'Plaidoyer & Lobbying',
    desc: 'Porter la voix des travailleurs auprès des instances décisionnelles continentales et internationales.',
    image: '/images/news_peace_justice.png', // Reusing generated image
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg>',
    items: [
      'Engagement avec l\'Union Africaine (UA)',
      'Suivi de la ZLECAF (AfCFTA)',
      'Lobbying pour la ratification des conventions de l\'OIT',
      'Dialogue avec les institutions financières internationales'
    ]
  },
  {
    title: 'Formation & Éducation',
    desc: 'Renforcer les capacités techniques et stratégiques des leaders et militants syndicaux.',
    image: '/images/news_women_rights.png', // Reusing generated image
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"></path><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"></path></svg>',
    items: [
      'Ateliers de planification stratégique',
      'Formation sur la négociation collective',
      'Éducation ouvrière et droits fondamentaux',
      'Développement de toolkits pédagogiques'
    ]
  },
  {
    title: 'Mobilisation & Solidarité',
    desc: 'Organiser l\'action collective pour défendre les libertés syndicales et le travail décent.',
    image: '/images/news_may_day.png', // Reusing generated image
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M23 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path></svg>',
    items: [
      'Célébration du 1er Mai (Fête du Travail)',
      'Campagnes de recrutement syndical',
      'Actions de solidarité inter-pays',
      'Mobilisation pour la protection sociale'
    ]
  }
]

const recentEvents = [
  {
    day: '01',
    month: 'MAI',
    tag: 'Mobilisation',
    title: 'Journée Internationale des Travailleurs',
    location: 'Afrique (Toutes régions)',
    desc: 'Mobilisation massive sous le thème du travail décent et de la justice sociale.'
  },
  {
    day: '15',
    month: 'AVR',
    tag: 'Formation',
    title: 'Atelier Régional sur l\'Économie Informelle',
    location: 'Nairobi, Kenya',
    desc: 'Session de renforcement des capacités pour l\'organisation des travailleurs du secteur informel.'
  },
  {
    day: '22',
    month: 'MAR',
    tag: 'Plaidoyer',
    title: 'Forum de Dialogue UA - Syndicats',
    location: 'Addis-Abeba, Éthiopie',
    desc: 'Discussions stratégiques sur l\'impact de la ZLECAF sur l\'emploi en Afrique.'
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

.category-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2.5rem;
}

.cat-card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0,0,0,0.05);
  transition: transform 0.3s ease;
}

.cat-card:hover { transform: translateY(-10px); }

.cat-card__img-wrapper {
  position: relative;
  height: 200px;
}

.cat-card__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.cat-card__icon {
  position: absolute;
  bottom: -25px;
  right: 25px;
  width: 50px;
  height: 50px;
  background: var(--color-primary);
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  padding: 10px;
}

.cat-card__content {
  padding: 1.25rem 1rem;
}

.cat-card__content h3 {
  font-size: 1.1rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 0.5rem;
}

.cat-card__content p {
  color: #666;
  margin-bottom: 1rem;
  font-size: 0.85rem;
  line-height: 1.5;
}

.cat-list {
  list-style: none;
  padding: 0;
}

.cat-list li {
  margin-bottom: 0.8rem;
  padding-left: 1.5rem;
  position: relative;
  font-weight: 600;
  font-size: 0.9rem;
  color: var(--color-secondary);
}

.cat-list li::before {
  content: '→';
  position: absolute;
  left: 0;
  color: var(--color-primary);
}

.recent-activities {
  background: var(--color-bg-light);
}

.activity-timeline {
  max-width: 900px;
  margin: 3rem auto 0;
}

.event-item {
  display: grid;
  grid-template-columns: 100px 1fr;
  gap: 2rem;
  background: white;
  margin-bottom: 1rem;
  padding: 1rem;
  border-radius: 12px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.02);
}

.event-date {
  background: var(--color-secondary);
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  padding: 1rem;
  height: 100px;
}

.event-date .day { font-size: 2rem; font-weight: 900; }
.event-date .month { font-size: 0.9rem; font-weight: 700; opacity: 0.8; }

.event-tag {
  display: inline-block;
  padding: 0.2rem 0.8rem;
  background: var(--color-bg-light);
  color: var(--color-primary);
  font-weight: 800;
  font-size: 0.75rem;
  border-radius: 50px;
  margin-bottom: 0.8rem;
  text-transform: uppercase;
}

.event-info h3 { font-size: 1rem; font-weight: 900; color: var(--color-secondary); margin-bottom: 0.3rem; }
.event-info p { color: #555; font-size: 0.9rem; margin-bottom: 0.5rem; }
.event-desc { margin-top: 1rem; line-height: 1.5; color: #666; }

@media (max-width: 1024px) {
  .category-grid { grid-template-columns: 1fr; }
}

@media (max-width: 640px) {
  .event-item { grid-template-columns: 1fr; text-align: center; }
  .event-date { width: 100px; margin: 0 auto; }
}
</style>
