<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">La Voix des Travailleurs</span>
        <h1 class="hero-sub__title">ACTUALITÉS</h1>
        <p class="hero-sub__subtitle">
          Déclarations officielles, communiqués de presse et échos des luttes syndicales à travers le continent.
        </p>
      </div>
    </section>

    <!-- NEWS FEED -->
    <section class="section news-feed">
      <div class="container news-layout">
        
        <!-- MAIN CONTENT -->
        <main class="news-main">
          <div class="featured-news">
            <div v-for="news in featuredNews" :key="news.title" class="news-card news-card--featured">
              <div class="news-card__img">
                <img :src="news.image" :alt="news.title" />
                <span class="news-tag">{{ news.tag }}</span>
              </div>
              <div class="news-card__content">
                <div class="news-date">{{ news.date }}</div>
                <h2>{{ news.title }}</h2>
                <p>{{ news.excerpt }}</p>
                <NuxtLink :to="news.link" class="btn-text">Lire la suite →</NuxtLink>
              </div>
            </div>
          </div>

          <div class="news-list">
            <div v-for="news in otherNews" :key="news.title" class="news-item">
              <div class="news-item__content">
                <div class="news-item__meta">
                  <span class="news-tag news-tag--small">{{ news.tag }}</span>
                  <span class="news-date">{{ news.date }}</span>
                </div>
                <h3>{{ news.title }}</h3>
                <p>{{ news.excerpt }}</p>
                <NuxtLink :to="news.link" class="link-voir-tout">Lire le communiqué ↗</NuxtLink>
              </div>
            </div>
          </div>
        </main>

        <!-- SIDEBAR -->
        <aside class="news-sidebar">
          <div class="sidebar-block">
            <h3>CATÉGORIES</h3>
            <ul class="category-list">
              <li v-for="cat in categories" :key="cat">
                <a href="#">{{ cat }}</a>
              </li>
            </ul>
          </div>

          <div class="sidebar-block newsletter-mini">
            <h3>NEWSLETTER</h3>
            <p>Recevez nos derniers communiqués directement par email.</p>
            <form @submit.prevent class="mini-form">
              <input type="email" placeholder="Votre email" />
              <button class="btn btn--primary btn--full">S'ABONNER</button>
            </form>
          </div>

          <div class="sidebar-block social-mini">
            <h3>SUIVEZ-NOUS</h3>
            <div class="social-links-mini">
              <a href="#">FB</a>
              <a href="#">TW</a>
              <a href="#">LN</a>
              <a href="#">YT</a>
            </div>
          </div>
        </aside>

      </div>
    </section>

    <TheFooter />
  </div>
</template>

<script setup>
const categories = ['Plaidoyer', 'Solidarité', 'Campagnes', 'Rapports', 'Coopération']

const featuredNews = [
  {
    tag: 'Déclaration',
    date: '1 Mai 2025',
    title: 'Message du 1er Mai : Paix et Stabilité pour l\'Industrialisation',
    excerpt: 'Le Secrétaire Général Joel Odigie appelle à une Afrique où la paix est le socle du travail décent et de la justice sociale.',
    image: '/images/news_may_day.png',
    link: '/ressources/actualites/may-day-2025'
  }
]

const otherNews = [
  {
    tag: 'Solidarité',
    date: '15 Octobre 2025',
    title: 'Solidarité avec le ZCTU : Non à la violation de la constitution au Zimbabwe',
    excerpt: 'La CSI-Afrique rejette fermement les tentatives d\'extension du mandat présidentiel au-delà des limites constitutionnelles.',
    link: '/ressources/actualites/zimbabwe-solidarity'
  },
  {
    tag: 'Plaidoyer',
    date: '20 Août 2025',
    title: 'ZLECAF : Pétition pour un protocole social et du travail',
    excerpt: 'Les syndicats africains demandent des clauses contraignantes pour protéger les droits des travailleurs dans le commerce continental.',
    link: '/ressources/actualites/afcfta-petition'
  },
  {
    tag: 'Droits',
    date: '5 Juillet 2025',
    title: 'Eswatini : Halte à la répression des libertés syndicales',
    excerpt: 'Appel international pour un dialogue national inclusif et l\'arrêt immédiat de l\'intimidation des leaders ouvriers.',
    link: '/ressources/actualites/eswatini-rights'
  },
  {
    tag: 'Campagne',
    date: '12 Juin 2025',
    title: 'Protection Sociale : Vers une portabilité pour les migrants',
    excerpt: 'Lancement d\'une nouvelle initiative pour garantir que les travailleurs mobiles ne perdent pas leurs droits à la retraite.',
    link: '/ressources/actualites/social-protection-migrants'
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

.news-layout {
  display: grid;
  grid-template-columns: 1fr 300px;
  gap: 4rem;
}

.news-card--featured {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0,0,0,0.05);
  margin-bottom: 4rem;
}

.news-card__img {
  position: relative;
  height: 400px;
}

.news-card__img img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.news-tag {
  position: absolute;
  top: 1.5rem;
  left: 1.5rem;
  background: var(--color-primary);
  color: white;
  padding: 0.4rem 1rem;
  font-weight: 800;
  text-transform: uppercase;
  font-size: 0.75rem;
  border-radius: 4px;
}

.news-card__content {
  padding: 3rem;
}

.news-card__content h2 {
  font-size: 2.2rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 1rem;
  line-height: 1.2;
}

.news-date {
  color: #888;
  font-weight: 700;
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
}

.news-card__content p {
  font-size: 1.1rem;
  color: #555;
  margin-bottom: 2rem;
  line-height: 1.6;
}

.news-list {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2.5rem;
}

.news-item {
  border-bottom: 1px solid #eee;
  padding-bottom: 2.5rem;
}

.news-item__meta {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
}

.news-tag--small {
  position: static;
  background: var(--color-bg-light);
  color: var(--color-primary);
}

.news-item h3 {
  font-size: 1.5rem;
  font-weight: 800;
  color: var(--color-secondary);
  margin-bottom: 1rem;
}

.news-item p {
  color: #666;
  margin-bottom: 1rem;
  line-height: 1.5;
}

.sidebar-block {
  background: var(--color-bg-light);
  padding: 2rem;
  border-radius: 12px;
  margin-bottom: 2rem;
}

.sidebar-block h3 {
  font-size: 1.1rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 1.5rem;
  border-bottom: 2px solid var(--color-primary);
  display: inline-block;
  padding-bottom: 0.3rem;
}

.category-list {
  list-style: none;
  padding: 0;
}

.category-list li {
  margin-bottom: 0.8rem;
}

.category-list a {
  font-weight: 700;
  color: #555;
  transition: color 0.3s ease;
}

.category-list a:hover {
  color: var(--color-primary);
}

.mini-form {
  margin-top: 1rem;
}

.mini-form input {
  width: 100%;
  padding: 0.8rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  margin-bottom: 1rem;
}

.btn--full { width: 100%; }

.social-links-mini {
  display: flex;
  gap: 1rem;
}

.social-links-mini a {
  width: 40px;
  height: 40px;
  background: white;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  font-weight: 900;
  font-size: 0.75rem;
  color: var(--color-secondary);
  box-shadow: 0 5px 10px rgba(0,0,0,0.05);
}

@media (max-width: 1024px) {
  .news-layout { grid-template-columns: 1fr; }
  .news-sidebar { display: grid; grid-template-columns: repeat(2, 1fr); gap: 2rem; }
}

@media (max-width: 768px) {
  .news-sidebar { grid-template-columns: 1fr; }
  .news-card__img { height: 250px; }
  .news-card__content { padding: 2rem 1.5rem; }
  .news-card__content h2 { font-size: 1.5rem; }
}
</style>
