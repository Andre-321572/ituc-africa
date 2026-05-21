<template>
  <div class="site">
    <TheNavbar />

    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">Domaines d'Action</span>
        <h1 class="hero-sub__title">NOS PROGRAMMES</h1>
        <p class="hero-sub__subtitle">
          Initiatives stratégiques visant à renforcer la dignité humaine, les droits syndicaux et la justice sociale sur le continent africain.
        </p>
      </div>
    </section>

    <section class="section programmes-list">
      <div class="container">
        <div class="programmes-grid">
          <div v-for="prog in programmes" :key="prog.title" class="prog-item">
            <div class="prog-item__icon" v-html="prog.icon"></div>
            <div class="prog-item__content">
              <h3>{{ prog.title }}</h3>
              <p>{{ prog.desc }}</p>
              <NuxtLink :to="prog.link" class="btn-text">En savoir plus →</NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<script setup>
const programmes = [
  {
    title: "Transformation Structurelle",
    desc: "Promouvoir une industrialisation durable et une diversification économique pour le développement de l'Afrique.",
    link: "/nos-actions/programmes/transformation",
    icon: '<svg width="40" height="40" fill="currentColor" viewBox="0 0 24 24"><path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/></svg>'
  },
  {
    title: "Égalité de Genre",
    desc: "Lutter contre les discriminations et promouvoir le leadership des femmes au sein du mouvement syndical.",
    link: "/nos-actions/programmes/genre",
    icon: '<svg width="40" height="40" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/></svg>'
  },
  {
    title: "Droits Humains et Syndicaux",
    desc: "Défendre la liberté d'association et lutter contre les violations des droits des travailleurs en Afrique.",
    link: "/nos-actions/programmes/droits",
    icon: '<svg width="40" height="40" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5-10-5-10 5z"/></svg>'
  },
  {
    title: "Climat et Environnement",
    desc: "Mobiliser pour une transition juste qui protège les emplois et l'environnement sur le continent.",
    link: "/nos-actions/programmes/climat",
    icon: '<svg width="40" height="40" fill="currentColor" viewBox="0 0 24 24"><path d="M12 3L2 12h3v8h14v-8h3L12 3z"/></svg>'
  },
  {
    title: "Travail des Jeunes",
    desc: "Autonomiser la jeunesse africaine et favoriser l'emploi décent pour les nouvelles générations de travailleurs.",
    link: "/nos-actions/programmes/jeunes",
    icon: '<svg width="40" height="40" fill="currentColor" viewBox="0 0 24 24"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg>'
  },
  {
    title: "Unité Syndicale",
    desc: "Renforcer la solidarité continentale en organisant les travailleurs et en unissant les centres syndicaux.",
    link: "/nos-actions/programmes/unite",
    icon: '<svg width="40" height="40" fill="currentColor" viewBox="0 0 24 24"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg>'
  },
  {
    title: "Protection Sociale",
    desc: "Plaider pour l'extension de la protection sociale universelle à tous les travailleurs, y compris l'économie informelle.",
    link: "/nos-actions/programmes/protection",
    icon: '<svg width="40" height="40" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/></svg>'
  },
  {
    title: "Paix et Sécurité",
    desc: "Soutenir la paix durable comme condition essentielle au développement social et aux droits des travailleurs.",
    link: "/nos-actions/programmes/paix",
    icon: '<svg width="40" height="40" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/></svg>'
  },
  {
    title: "Santé et Sécurité",
    desc: "Garantir un environnement de travail sûr et sain pour tous les travailleurs africains.",
    link: "/nos-actions/programmes/sante",
    icon: '<svg width="40" height="40" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5-10-5-10 5z"/></svg>'
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

.programmes-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2.5rem;
}

.prog-item {
  background: white;
  padding: 2.5rem;
  border-radius: 8px;
  border: 1px solid rgba(0,0,0,0.05);
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
}

.prog-item:hover {
  box-shadow: 0 10px 30px rgba(0,0,0,0.05);
  border-color: var(--color-primary);
}

.prog-item__icon {
  color: var(--color-primary);
  margin-bottom: 1.5rem;
}

.prog-item__content h3 {
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 1rem;
  font-size: 1.4rem;
}

.prog-item__content p {
  color: #555;
  line-height: 1.6;
  margin-bottom: 2rem;
}

.btn-text {
  font-weight: 800;
  color: var(--color-primary);
  text-transform: uppercase;
  font-size: 0.85rem;
}

@media (max-width: 1024px) {
  .programmes-grid { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 640px) {
  .programmes-grid { grid-template-columns: 1fr; }
}
</style>
