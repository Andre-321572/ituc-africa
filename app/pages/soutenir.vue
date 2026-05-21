<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub hero-soutenir">
      <div class="container">
        <span class="badge badge--white">Agir Ensemble</span>
        <h1 class="hero-sub__title">NOUS SOUTENIR</h1>
        <p class="hero-sub__subtitle">
          Chaque geste de solidarité renforce la lutte pour la dignité des travailleurs africains. Découvrez comment vous pouvez contribuer.
        </p>
      </div>
    </section>

    <!-- SUPPORT METHODS -->
    <section class="section support-methods">
      <div class="container">
        <div class="support-grid">
          
          <div class="support-card">
            <div class="support-icon">🤝</div>
            <h3>REJOINDRE UN SYNDICAT</h3>
            <p>La force des travailleurs réside dans leur union. Si vous êtes un travailleur en Afrique, la meilleure façon de nous soutenir est de rejoindre une organisation syndicale affiliée dans votre pays.</p>
            <NuxtLink to="/a-propos/affilies" class="btn btn--primary">TROUVER UN AFFILIÉ</NuxtLink>
          </div>

          <div class="support-card">
            <div class="support-icon">📢</div>
            <h3>AMPLIFIER NOS LUTTES</h3>
            <p>Aidez-nous à porter la voix des travailleurs plus loin. Partagez nos campagnes, signez nos pétitions et participez aux actions de solidarité numérique.</p>
            <div class="social-btns">
              <a href="#" class="btn-s">FACEBOOK</a>
              <a href="#" class="btn-s">TWITTER</a>
            </div>
          </div>

          <div class="support-card">
            <div class="support-icon">💼</div>
            <h3>PARTENARIATS</h3>
            <p>Vous représentez une organisation internationale, une ONG ou une institution ? Collaborez avec nous sur des projets de développement social et de justice économique.</p>
            <NuxtLink to="/contact" class="btn btn--secondary">DEVENIR PARTENAIRE</NuxtLink>
          </div>

        </div>
      </div>
    </section>

    <!-- IMPACT SECTION -->
    <section class="section impact-why">
      <div class="container">
        <div class="impact-inner">
          <div class="impact-content">
            <h2 class="section-title">POURQUOI NOUS SOUTENIR ?</h2>
            <p>En soutenant la CSI-Afrique, vous contribuez directement à :</p>
            <ul class="impact-list">
              <li><strong>Défendre</strong> les libertés syndicales menacées.</li>
              <li><strong>Promouvoir</strong> l'égalité des genres et le leadership des femmes.</li>
              <li><strong>Garantir</strong> une protection sociale pour les plus vulnérables.</li>
              <li><strong>Lutter</strong> contre l'exploitation et le travail précaire.</li>
            </ul>
          </div>
          <div class="impact-visual">
            <div class="quote-box">
              <p>"La solidarité n'est pas un sentiment de compassion vague, mais une détermination ferme de persévérer pour le bien commun."</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- DIRECT CONTACT -->
    <section class="section direct-contact">
      <div class="container text-center">
        <div class="contact-card-large">
          <h2>BESOIN DE PLUS D'INFORMATIONS ?</h2>
          <p>Notre équipe est à votre disposition pour discuter des modalités de soutien et de collaboration.</p>
          <div class="contact-info-grid">
            <div class="ci-item">
              <strong>Email</strong>
              <span>info@ituc-africa.org</span>
            </div>
            <div class="ci-item">
              <strong>Téléphone</strong>
              <span>(+228) 22 25 03 90</span>
            </div>
            <div class="ci-item">
              <strong>Siège</strong>
              <span>Lomé, Togo</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <TheFooter />
  </div>
</template>

<style scoped>
.hero-soutenir {
  background: linear-gradient(rgba(200, 146, 58, 0.9), rgba(218, 83, 44, 0.9)), url('https://www.transparenttextures.com/patterns/pinstriped-suit.png');
  color: white;
}

.support-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 3rem;
}

.support-card {
  background: white;
  padding: 2rem 1.25rem;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 15px 40px rgba(0,0,0,0.05);
  transition: transform 0.3s ease;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.support-card:hover { transform: translateY(-10px); }

.support-icon { font-size: 2rem; margin-bottom: 1rem; }

.support-card h3 {
  font-size: 1.1rem;
  font-weight: 900;
  color: var(--color-secondary);
  margin-bottom: 1rem;
}

.support-card p {
  color: #555;
  line-height: 1.6;
  margin-bottom: 1.5rem;
  font-size: 0.85rem;
}

.social-btns {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.btn-s {
  padding: 0.6rem 1rem;
  background: var(--color-bg-light);
  color: var(--color-secondary);
  font-weight: 900;
  font-size: 0.7rem;
  border-radius: 4px;
}

.impact-why {
  background: var(--color-bg-light);
}

.impact-inner {
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 5rem;
  align-items: center;
}

.impact-list {
  list-style: none;
  padding: 0;
  margin-top: 2rem;
}

.impact-list li {
  margin-bottom: 1.2rem;
  padding-left: 2rem;
  position: relative;
  font-size: 1.1rem;
}

.impact-list li::before {
  content: '✔';
  position: absolute;
  left: 0;
  color: var(--color-primary);
  font-weight: 900;
}

.quote-box {
  background: white;
  padding: 3rem;
  border-left: 10px solid var(--color-primary);
  border-radius: 8px;
  font-style: italic;
  font-size: 1.4rem;
  color: var(--color-secondary);
  box-shadow: 0 10px 30px rgba(0,0,0,0.05);
}

.contact-card-large {
  background: var(--color-secondary);
  color: white;
  padding: 2.5rem;
  border-radius: 20px;
}

.contact-card-large h2 { font-size: 2.5rem; font-weight: 900; margin-bottom: 1rem; }
.contact-card-large p { font-size: 1.2rem; margin-bottom: 3rem; opacity: 0.8; }

.contact-info-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  border-top: 1px solid rgba(255,255,255,0.1);
  padding-top: 3rem;
}

.ci-item strong { display: block; font-size: 0.8rem; text-transform: uppercase; color: var(--color-primary); margin-bottom: 0.5rem; }
.ci-item span { font-size: 1.2rem; font-weight: 700; }

@media (max-width: 1024px) {
  .support-grid, .impact-inner, .contact-info-grid { grid-template-columns: 1fr; }
  .contact-card-large { padding: 3rem 2rem; }
}
</style>
