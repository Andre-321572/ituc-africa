<template>
  <div class="site">
    <TheNavbar />

    <!-- HERO SUBPAGE -->
    <section class="hero-sub">
      <div class="container">
        <span class="badge badge--primary">Restons Connectés</span>
        <h1 class="hero-sub__title">CONTACTEZ-NOUS</h1>
        <p class="hero-sub__subtitle">
          Vous avez une question, une demande de partenariat ou souhaitez nous soumettre une information ? Notre équipe vous répondra dans les plus brefs délais.
        </p>
      </div>
    </section>

    <!-- CONTACT SECTION -->
    <section class="section contact-main">
      <div class="container">
        <div class="contact-grid">
          
          <!-- CONTACT FORM -->
          <div class="contact-form-wrapper">
            <h2 class="section-title">ENVOYEZ UN MESSAGE</h2>
            <form @submit.prevent class="contact-form">
              <div class="form-row">
                <div class="form-group">
                  <label for="name">Nom Complet</label>
                  <input type="text" id="name" placeholder="Votre nom" required />
                </div>
                <div class="form-group">
                  <label for="email">Email professionnel</label>
                  <input type="email" id="email" placeholder="votre@email.com" required />
                </div>
              </div>
              <div class="form-group">
                <label for="org">Organisation / Affilié</label>
                <input type="text" id="org" placeholder="Nom de votre organisation" />
              </div>
              <div class="form-group">
                <label for="subject">Sujet</label>
                <select id="subject">
                  <option value="general">Information Générale</option>
                  <option value="affiliation">Demande d'Affiliation</option>
                  <option value="partnership">Partenariat / Coopération</option>
                  <option value="press">Presse & Médias</option>
                  <option value="alrei">Recherche (ALREI)</option>
                </select>
              </div>
              <div class="form-group">
                <label for="message">Votre Message</label>
                <textarea id="message" rows="6" placeholder="Comment pouvons-nous vous aider ?"></textarea>
              </div>
              <button type="submit" class="btn btn--primary btn--full">ENVOYER LE MESSAGE</button>
            </form>
          </div>

          <!-- CONTACT INFO -->
          <div class="contact-info-sidebar">
            <div class="info-block">
              <h3>NOTRE SIÈGE</h3>
              <p>Route Internationale d'Atakpamé,<br>Centre FOPADESC Agoè-Nyivé,<br>BP 4401, Lomé - TOGO</p>
            </div>
            
            <div class="info-block">
              <h3>COORDONNÉES</h3>
              <div class="contact-links">
                <a href="mailto:info@ituc-africa.org" class="c-link">
                  <span class="c-icon">✉</span> info@ituc-africa.org
                </a>
                <a href="tel:+22822250390" class="c-link">
                  <span class="c-icon">📞</span> (+228) 22 25 03 90
                </a>
              </div>
            </div>

            <div class="info-block">
              <h3>RÉSEAUX SOCIAUX</h3>
              <div class="social-grid-large">
                <a href="#" class="s-btn fb">Facebook</a>
                <a href="#" class="s-btn tw">Twitter (X)</a>
                <a href="#" class="s-btn ln">LinkedIn</a>
                <a href="#" class="s-btn yt">YouTube</a>
              </div>
            </div>

            <div class="info-block map-box">
               <div class="map-placeholder">
                 <span>LOMÉ, TOGO</span>
               </div>
            </div>
          </div>

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

.contact-grid {
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  gap: 5rem;
}

.contact-form {
  margin-top: 2rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  font-weight: 800;
  color: var(--color-secondary);
  margin-bottom: 0.5rem;
  font-size: 0.9rem;
  text-transform: uppercase;
}

.form-group input, 
.form-group select, 
.form-group textarea {
  width: 100%;
  padding: 1rem;
  border: 2px solid #eee;
  border-radius: 8px;
  font-family: inherit;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

.form-group input:focus, 
.form-group select:focus, 
.form-group textarea:focus {
  border-color: var(--color-primary);
  outline: none;
}

.btn--full { width: 100%; padding: 1.2rem; font-size: 1.1rem; }

.contact-info-sidebar {
  background: var(--color-bg-light);
  padding: 3rem;
  border-radius: 12px;
}

.info-block {
  margin-bottom: 3rem;
}

.info-block h3 {
  font-size: 1.1rem;
  font-weight: 900;
  color: var(--color-primary);
  margin-bottom: 1rem;
  letter-spacing: 1px;
}

.info-block p {
  font-size: 1.1rem;
  line-height: 1.6;
  color: var(--color-secondary);
  font-weight: 600;
}

.contact-links {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.c-link {
  display: flex;
  align-items: center;
  gap: 1rem;
  font-weight: 700;
  color: var(--color-secondary);
  font-size: 1.1rem;
}

.c-icon {
  width: 35px;
  height: 35px;
  background: white;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  color: var(--color-primary);
}

.social-grid-large {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.s-btn {
  padding: 0.8rem;
  background: white;
  text-align: center;
  border-radius: 6px;
  font-weight: 800;
  font-size: 0.8rem;
  color: var(--color-secondary);
  box-shadow: 0 4px 10px rgba(0,0,0,0.05);
}

.map-box {
  height: 200px;
  border-radius: 8px;
  overflow: hidden;
  background: #ddd;
}

.map-placeholder {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(rgba(27, 61, 27, 0.2), rgba(27, 61, 27, 0.2)), url('https://www.transparenttextures.com/patterns/pinstriped-suit.png');
  color: var(--color-secondary);
  font-weight: 900;
  letter-spacing: 2px;
}

@media (max-width: 1024px) {
  .contact-grid { grid-template-columns: 1fr; }
  .contact-info-sidebar { order: -1; }
}

@media (max-width: 640px) {
  .form-row { grid-template-columns: 1fr; }
}
</style>
