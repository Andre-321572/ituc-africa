<template>
  <div class="site">

    <!-- NAVBAR -->
    <TheNavbar />

    <!-- HERO -->
    <section class="hero">
      <div class="hero__bg">
        <img
          src="/images/hero.png"
          alt="Travailleurs africains"
          class="hero__img"
        />
        <div class="hero__overlay"></div>
      </div>
      <div class="hero__content container">
        <span class="hero__badge">{{ $t('hero.panafrican_badge') }}</span>
        <h1 class="hero__title">{{ $t('hero.title') }}</h1>
        <p class="hero__subtitle">
          {{ $t('hero.subtitle') }}
        </p>
        <div class="hero__ctas">
          <NuxtLink :to="localePath('/ressources/documents')" class="btn btn--outline-white">{{ $t('hero.cta_report') }}</NuxtLink>
          <NuxtLink :to="localePath('/soutenir')" class="btn btn--primary">{{ $t('hero.cta_join') }}</NuxtLink>
        </div>
      </div>
    </section>

    <!-- ACTUALITÉS -->
    <section class="section news">
      <div class="container">
        <div class="section__header">
          <div>
            <span class="badge badge--primary">Nos actualités</span>
            <h2 style="font-size: 2.5rem; font-weight: 900; color: var(--color-secondary);">DERNIERS ÉVÉNEMENTS</h2>
          </div>
          <a href="#" class="link-voir-tout">Voir tout ↗</a>
        </div>
        <div class="news__grid">
          <article v-for="article in articles" :key="article.id" class="news-card">
            <div class="news-card__img-wrap">
              <img :src="article.img" :alt="article.title" class="news-card__img" />
              <span class="news-card__date">{{ article.date }}</span>
            </div>
            <div class="news-card__body">
              <span class="badge" :class="`badge--${article.tagColor}`">{{ article.tag }}</span>
              <h3 class="news-card__title">{{ article.title }}</h3>
              <p class="news-card__desc">{{ article.desc }}</p>
              <a :href="article.url" class="news-card__link">Lire l'article →</a>
            </div>
          </article>
        </div>
      </div>
    </section>

    <!-- MISSION -->
    <section class="section mission">
      <div class="container mission__inner">
        <h2 class="mission__title">{{ $t('mission.title') }}</h2>
        <p class="mission__text">
          {{ $t('mission.text1') }}
        </p>
        <p class="mission__text">
          {{ $t('mission.text2') }}
        </p>
        <NuxtLink :to="localePath('/a-propos')" class="link-decouvrir">{{ $t('mission.cta_more') }}</NuxtLink>
      </div>
    </section>

    <!-- IMPACT -->
    <section class="section impact">
      <div class="container">
        <div class="section__header">
          <span class="badge badge--primary">{{ $t('impact.badge') }}</span>
        </div>
        <div class="impact__grid">
          <!-- Carte stats -->
          <div class="impact-card impact-card--light">
            <h3 class="impact-card__title">{{ $t('impact.stats_title') }}</h3>
            <p class="impact-card__subtitle">{{ $t('impact.stats_subtitle') }}</p>
            <div class="impact-stats">
              <div v-for="stat in stats" :key="stat.label" class="impact-stat">
                <div class="impact-stat__icon-wrap" v-html="stat.icon"></div>
                <div>
                  <strong class="impact-stat__value">{{ stat.value }}</strong>
                  <div class="impact-stat__label">{{ $t(`impact.stats.${stat.key}`) }}</div>
                </div>
              </div>
            </div>
          </div>

          <!-- Carte Afrique -->
          <div class="impact-card impact-card--dark">
            <h3 class="impact-card__title--light">{{ $t('impact.map_title') }}</h3>
            <p class="impact-card__subtitle--light">{{ $t('impact.map_subtitle') }}</p>
            <div class="africa-map">
              <svg viewBox="0 0 300 340" xmlns="http://www.w3.org/2000/svg" class="africa-map__svg">
                <path d="M100,20 L150,15 L200,25 L230,60 L240,120 L230,180 L200,250 L160,300 L140,320 L120,300 L80,250 L60,180 L50,120 L60,60 L100,20 Z" fill="#2E6B2E" stroke="#4CAF50" stroke-width="2"/>
                <circle v-for="i in 15" :key="i" :cx="60 + Math.random()*150" :cy="40 + Math.random()*250" r="4" fill="#DA532C">
                  <animate attributeName="opacity" values="1;0.4;1" dur="2s" repeatCount="indefinite" :begin="i*0.2 + 's'" />
                </circle>
              </svg>
            </div>
            <select class="impact-card__select" @change="onRegionChange">
              <option value="">Choisir une région africaine</option>
              <option value="west">Afrique de l'Ouest</option>
              <option value="east">Afrique de l'Est</option>
              <option value="central">Afrique Centrale</option>
              <option value="north">Afrique du Nord</option>
              <option value="south">Afrique Australe</option>
            </select>
          </div>
        </div>
      </div>
    </section>

    <!-- DOMAINES D'ACTION -->
    <section class="section programmes">
      <div class="container">
        <div class="section__header--center">
          <span class="badge badge--primary">Nos Domaines d'Action</span>
          <h2 class="programmes__title">COMMENT NOUS AGISSONS</h2>
        </div>
        <div class="programmes__grid">
          <div v-for="prog in programmes" :key="prog.key" class="prog-card">
            <div class="prog-card__icon" v-html="prog.icon"></div>
            <h4 class="prog-card__label">{{ $t(`programmes.${prog.key}`) }}</h4>
          </div>
        </div>
      </div>
    </section>

    <!-- SECRÉTAIRE GÉNÉRAL -->
    <section class="section sg-section">
      <div class="container sg-section__inner">
        <div class="sg-section__img-wrap">
          <img
            src="https://ituc-africa.org/IMG/logo/sg2-csi.jpg"
            alt="Joel Akhator Odigie"
            class="sg-section__img"
          />
        </div>
        <div class="sg-section__content">
          <span class="badge badge--primary">Le mot du Secrétaire Général</span>
          <h2 class="sg-section__title">Joel Akhator Odigie</h2>
          <p class="sg-section__role">Secrétaire Général — CSI-Afrique</p>
          <blockquote class="sg-section__quote">
            "La force du mouvement syndical africain réside dans notre unité. 
            Ensemble, nous construisons un avenir où chaque travailleur est respecté."
          </blockquote>
          <NuxtLink to="/communications/declarations" class="btn btn--outline-dark">Toutes les déclarations →</NuxtLink>
        </div>
      </div>
    </section>

    <!-- NEWSLETTER -->
    <section class="newsletter">
      <div class="container newsletter__inner">
        <div class="newsletter__text">
          <h2 class="newsletter__title">RESTEZ INFORMÉ·E</h2>
          <p class="newsletter__subtitle">Recevez nos actualités et communiqués syndicaux</p>
        </div>
        <form class="newsletter__form" @submit.prevent="subscribe">
          <input type="email" placeholder="Votre adresse email" class="newsletter__input" required />
          <button type="submit" class="btn btn--primary">S'INSCRIRE</button>
        </form>
      </div>
    </section>

    <TheFooter />

  </div>
</template>

<script setup>
const localePath = useLocalePath()
const menuOpen = ref(false)
const activeMenu = ref(null)

const articles = [
  {
    id: 1,
    img: '/images/news-1.png',
    date: '1 Mai 2026',
    tag: 'Journée des Travailleurs',
    tagColor: 'green',
    title: "1er MAI 2026 : Bâtir le pouvoir des travailleurs pour le renouveau de l'Afrique",
    desc: "Mettre fin aux inégalités, sécuriser la paix et s'engager pour l'industrialisation de l'Afrique.",
    url: '#'
  },
  {
    id: 2,
    img: '/images/news-2.png',
    date: '15 Avril 2026',
    tag: 'Paix & Justice',
    tagColor: 'blue',
    title: "Appel des travailleurs africains pour la paix et la justice au Moyen-Orient",
    desc: "Par le dialogue, la diplomatie et la dignité pour toutes et tous.",
    url: '#'
  },
  {
    id: 3,
    img: '/images/news-3.png',
    date: '8 Mars 2026',
    tag: 'Droits des Femmes',
    tagColor: 'red',
    title: "Journée Internationale des Femmes 2026 : Droits, Justice, Action",
    desc: "Pour toutes les femmes et filles : droits, justice et action concrète.",
    url: '#'
  }
]

const stats = [
  { 
    key: 'members',
    value: '18M', 
    label: 'MEMBRES DÉCLARÉS', 
    icon: '<svg width="30" height="30" fill="currentColor" viewBox="0 0 24 24"><path d="M16 11c1.66 0 2.99-1.34 2.99-3S17.66 5 16 5s-3 1.34-3 3 1.34 3 3 3zm-8 0c1.66 0 2.99-1.34 2.99-3S9.66 5 8 5 5 6.34 5 8s1.34 3 3 3zm0 2c-2.33 0-7 1.17-7 3.5V19h14v-2.5c0-2.33-4.67-3.5-7-3.5zm8 0c-.29 0-.62.02-.97.05 1.16.84 1.97 1.97 1.97 3.45V19h6v-2.5c0-2.33-4.67-3.5-7-3.5z"/></svg>' 
  },
  { 
    key: 'countries',
    value: '52', 
    label: 'PAYS AFRICAINS', 
    icon: '<svg width="30" height="30" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5-10-5-10 5z"/></svg>' 
  },
  { 
    key: 'centers',
    value: '107', 
    label: 'CENTRES SYNDICAUX', 
    icon: '<svg width="30" height="30" fill="currentColor" viewBox="0 0 24 24"><path d="M12 7V3H2v18h20V7H12zM6 19H4v-2h2v2zm0-4H4v-2h2v2zm0-4H4V9h2v2zm0-4H4V5h2v2zm10 12h-2v-2h2v2zm0-4h-2v-2h2v2zm0-4h-2V9h2v2zm0-4h-2V5h2v2zm4 12h-2v-2h2v2zm0-4h-2v-2h2v2z"/></svg>' 
  }
]

const programmes = [
  { key: 'structural', icon: '<svg width="30" height="30" fill="#DA532C" viewBox="0 0 24 24"><path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/></svg>' },
  { key: 'gender', icon: '<svg width="30" height="30" fill="#DA532C" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/></svg>' },
  { key: 'rights', icon: '<svg width="30" height="30" fill="#DA532C" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/></svg>' },
  { key: 'climate', icon: '<svg width="30" height="30" fill="#DA532C" viewBox="0 0 24 24"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5-10-5-10 5z"/></svg>' },
  { key: 'youth', icon: '<svg width="30" height="30" fill="#DA532C" viewBox="0 0 24 24"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg>' },
  { key: 'unity', icon: '<svg width="30" height="30" fill="#DA532C" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/></svg>' },
  { key: 'social', icon: '<svg width="30" height="30" fill="#DA532C" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/></svg>' },
  { key: 'peace', icon: '<svg width="30" height="30" fill="#DA532C" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/></svg>' },
  { key: 'health', icon: '<svg width="30" height="30" fill="#DA532C" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/></svg>' }
]

const onRegionChange = (event) => {
  console.log('Region changed to:', event.target.value)
  // Logic to highlight region on SVG would go here
}

const subscribe = () => {
  alert('Merci pour votre inscription à notre newsletter !')
}
</script>

<style scoped>
.chevron {
  font-size: 0.7rem;
  opacity: 0.5;
}
</style>
