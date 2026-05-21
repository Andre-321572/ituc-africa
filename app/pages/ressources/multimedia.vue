<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">Images & Sons</span>
        <h1 class="hero-sub__title">MULTIMÉDIA</h1>
        <p class="hero-sub__subtitle">
          Vivez l'action syndicale en images à travers nos galeries photos, vidéos et productions audiovisuelles.
        </p>
      </div>
    </section>

    <!-- FEATURED VIDEO -->
    <section class="section featured-video">
      <div class="container">
        <h2 class="section-title text-center">À LA UNE : AFRICAN WORKERS TV</h2>
        <div class="video-container">
          <div class="video-wrapper">
             <div class="video-placeholder">
               <div class="play-btn">▶</div>
               <p>Regardez le récapitulatif du 5ème Congrès de la CSI-Afrique</p>
             </div>
          </div>
        </div>
      </div>
    </section>

    <!-- VIDEO GALLERY -->
    <section class="section video-gallery">
      <div class="container">
        <div class="section-header-flex">
          <h2 class="section-title">VIDÉOS RÉCENTES</h2>
          <a href="https://www.youtube.com/@AfricanWorkersTV" target="_blank" class="btn btn--outline">VOIR SUR YOUTUBE</a>
        </div>
        <div class="video-grid">
          <div v-for="video in videos" :key="video.title" class="video-item">
            <div class="video-thumb">
              <img :src="video.thumb" :alt="video.title" />
              <span class="duration">{{ video.duration }}</span>
            </div>
            <div class="video-info">
              <h3>{{ video.title }}</h3>
              <p>{{ video.category }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- PHOTO GALLERY -->
    <section class="section photo-gallery">
      <div class="container">
        <h2 class="section-title">ALBUMS PHOTOS</h2>
        <div class="photo-grid">
          <div v-for="album in albums" :key="album.title" class="photo-item">
            <div class="photo-wrap">
              <img :src="album.image" :alt="album.title" />
              <div class="photo-overlay">
                <span class="count">{{ album.count }} Photos</span>
                <button class="btn btn--white btn--sm">VOIR L'ALBUM</button>
              </div>
            </div>
            <h3>{{ album.title }}</h3>
          </div>
        </div>
      </div>
    </section>

    <!-- SOCIAL CHANNELS -->
    <section class="section social-channels">
      <div class="container text-center">
        <h2>REJOIGNEZ LA COMMUNAUTÉ</h2>
        <div class="channels-grid">
          <a href="#" class="channel-card yt">
            <div class="icon">YT</div>
            <span>African Workers TV</span>
          </a>
          <a href="#" class="channel-card fb">
            <div class="icon">FB</div>
            <span>CSI-Afrique Official</span>
          </a>
          <a href="#" class="channel-card tw">
            <div class="icon">TW</div>
            <span>@ituc_africa</span>
          </a>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<script setup>
const videos = [
  { title: 'TUTT : Trade Union Trade Talks #1', category: 'Économie', duration: '12:45', thumb: '/images/hero.png' },
  { title: 'New Year School 2025 Highlights', category: 'Éducation', duration: '05:20', thumb: '/images/news_women_rights.png' },
  { title: 'Solidarity with Swaziland Workers', category: 'Droits', duration: '08:15', thumb: '/images/news_peace_justice.png' },
  { title: 'Just Transition Campaign Launch', category: 'Climat', duration: '15:30', thumb: '/images/news_may_day.png' }
]

const albums = [
  { title: '5ème Congrès Ordinaire', image: '/images/news_may_day.png', count: 124 },
  { title: 'Atelier ZLECAF - Nairobi', image: '/images/news_peace_justice.png', count: 45 },
  { title: 'Célébration du 1er Mai 2025', image: '/images/hero.png', count: 89 },
  { title: 'Sommet Jeunesse Syndicale', image: '/images/news_women_rights.png', count: 67 }
]
</script>

<style scoped>
.hero-sub {
  background-color: var(--color-secondary);
  color: var(--color-white);
  padding: 6rem 0;
  text-align: center;
}

.featured-video {
  background: #0f1a0f; /* Very dark green */
  color: white;
}

.featured-video .section-title { color: white; margin-bottom: 3rem; }

.video-container {
  max-width: 1000px;
  margin: 0 auto;
}

.video-wrapper {
  position: relative;
  padding-bottom: 56.25%; /* 16:9 */
  height: 0;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 20px 50px rgba(0,0,0,0.3);
}

.video-placeholder {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('/images/hero.png');
  background-size: cover;
  background-position: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}

.play-btn {
  width: 80px;
  height: 80px;
  background: var(--color-primary);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  margin-bottom: 1.5rem;
  transition: transform 0.3s ease;
}

.video-placeholder:hover .play-btn { transform: scale(1.1); }

.section-header-flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 3rem;
}

.video-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
}

.video-item { cursor: pointer; }

.video-thumb {
  position: relative;
  height: 100px;
  border-radius: 8px;
  overflow: hidden;
  margin-bottom: 1rem;
}

.video-thumb img { width: 100%; height: 100%; object-fit: cover; }

.duration {
  position: absolute;
  bottom: 0.5rem;
  right: 0.5rem;
  background: rgba(0,0,0,0.8);
  color: white;
  padding: 0.2rem 0.5rem;
  font-size: 0.7rem;
  font-weight: 800;
  border-radius: 4px;
}

.video-info h3 {
  font-size: 0.85rem;
  font-weight: 800;
  color: var(--color-secondary);
  margin-bottom: 0.3rem;
  line-height: 1.3;
}

.video-info p {
  color: var(--color-primary);
  font-weight: 700;
  font-size: 0.75rem;
  text-transform: uppercase;
}

.photo-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
}

.photo-wrap {
  position: relative;
  height: 150px;
  border-radius: 12px;
  overflow: hidden;
  margin-bottom: 1rem;
}

.photo-wrap img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.5s ease; }

.photo-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(27, 61, 27, 0.8);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.photo-item:hover .photo-overlay { opacity: 1; }
.photo-item:hover img { transform: scale(1.1); }

.photo-overlay .count { color: white; font-weight: 800; margin-bottom: 1rem; }

.photo-item h3 {
  font-size: 0.9rem;
  font-weight: 900;
  color: var(--color-secondary);
  text-align: center;
}

.social-channels h2 { font-size: 2.5rem; font-weight: 900; color: var(--color-secondary); margin-bottom: 3rem; }

.channels-grid {
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
}

.channel-card {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  padding: 0.75rem 1.5rem;
  background: white;
  border-radius: 50px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.05);
  transition: transform 0.3s ease;
  font-weight: 900;
  font-size: 0.85rem;
  color: var(--color-secondary);
}

.channel-card:hover { transform: translateY(-10px); }

.channel-card .icon {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 0.8rem;
}

.yt .icon { background: #FF0000; }
.fb .icon { background: #1877F2; }
.tw .icon { background: #000000; }

@media (max-width: 1024px) {
  .video-grid, .photo-grid { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 640px) {
  .video-grid, .photo-grid { grid-template-columns: 1fr; }
  .channel-card { width: 100%; padding: 1rem 2rem; }
}
</style>
