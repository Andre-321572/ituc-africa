<template>
  <div class="site">
    <TheNavbar />

    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">S'informer & Apprendre</span>
        <h1 class="hero-sub__title">RESSOURCES</h1>
        <p class="hero-sub__subtitle">
          Le centre d'information de la CSI-Afrique : actualités, documentation technique et contenus multimédias.
        </p>
      </div>
    </section>

    <section class="section res-hub">
      <div class="container">
        <div class="res-grid">
          <NuxtLink to="/ressources/actualites" class="res-hub-card">
            <div class="res-hub-card__icon">📰</div>
            <h3>Actualités</h3>
            <p>Suivez les derniers communiqués, déclarations et échos des luttes syndicales sur le continent.</p>
            <span class="btn-text">Explorer →</span>
          </NuxtLink>

          <NuxtLink to="/ressources/documents" class="res-hub-card">
            <div class="res-hub-card__icon">📂</div>
            <h3>Documents & Rapports</h3>
            <p>Accédez à notre bibliothèque de rapports de recherche, documents de gouvernance et positions politiques.</p>
            <span class="btn-text">Explorer →</span>
          </NuxtLink>

          <NuxtLink to="/ressources/multimedia" class="res-hub-card">
            <div class="res-hub-card__icon">🎬</div>
            <h3>Multimédia</h3>
            <p>Vivez l'action syndicale en images à travers nos galeries photos, vidéos et productions audiovisuelles.</p>
            <span class="btn-text">Explorer →</span>
          </NuxtLink>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<style scoped>
.hero-sub {
  background-color: var(--color-secondary);
  color: var(--color-white);
  padding: 6rem 0;
  text-align: center;
}

.res-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2.5rem;
}

.res-hub-card {
  background: white;
  padding: 2rem 1.5rem;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 10px 30px rgba(0,0,0,0.05);
  transition: all 0.3s ease;
  display: block;
  text-decoration: none;
  border-top: 5px solid transparent;
}

.res-hub-card:hover {
  transform: translateY(-10px);
  border-color: var(--color-primary);
  box-shadow: 0 20px 50px rgba(0,0,0,0.1);
}

.res-hub-card__icon {
  font-size: 2rem;
  margin-bottom: 1rem;
}

.res-hub-card h3 {
  font-size: 1.2rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 1rem;
}

.res-hub-card p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 1.5rem;
  font-size: 0.85rem;
}

@media (max-width: 1024px) {
  .res-grid { grid-template-columns: 1fr; }
}
</style>
