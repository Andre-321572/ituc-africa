<script setup>
const { locale, setLocale, t } = useI18n()
const localePath = useLocalePath()
const menuOpen = ref(false)
const activeMenu = ref(null)

const switchLanguage = (lang) => {
  setLocale(lang)
}
</script>

<template>
  <header class="navbar">
    <div class="navbar__top">
      <div class="container navbar__top-inner">
        <div class="navbar__lang">
          <button @click="switchLanguage('fr')" :class="{ active: locale === 'fr' }">FR</button>
          <span>|</span>
          <button @click="switchLanguage('en')" :class="{ active: locale === 'en' }">EN</button>
        </div>
        <NuxtLink :to="localePath('/soutenir')" class="btn btn--primary btn--xs">{{ $t('nav.support') }}</NuxtLink>
      </div>
    </div>
    <div class="navbar__inner">
      <NuxtLink :to="localePath('/')" class="navbar__brand">
        <img
          src="https://ituc-africa.org/IMG/logo/siteon0.jpg"
          alt="CSI-Afrique Logo"
          class="navbar__logo"
        />
        <div class="navbar__brand-text">
          <span class="navbar__name">CSI-Afrique</span>
          <span class="navbar__tagline">{{ $t('hero.tagline') }}</span>
        </div>
      </NuxtLink>

      <nav class="navbar__nav">
        <div class="navbar__item" @mouseenter="activeMenu = 'about'" @mouseleave="activeMenu = null">
          <NuxtLink :to="localePath('/a-propos')" class="navbar__link">
            {{ $t('nav.about') }} <span class="chevron">▾</span>
          </NuxtLink>
          <div class="navbar__dropdown" :class="{ visible: activeMenu === 'about' }">
            <NuxtLink :to="localePath('/a-propos')">{{ $t('nav.about_org') }}</NuxtLink>
            <NuxtLink :to="localePath('/a-propos/affilies')">{{ $t('nav.about_affiliates') }}</NuxtLink>
            <NuxtLink :to="localePath('/a-propos/valeurs')">{{ $t('nav.about_values') }}</NuxtLink>
          </div>
        </div>
        <div class="navbar__item" @mouseenter="activeMenu = 'actions'" @mouseleave="activeMenu = null">
          <NuxtLink :to="localePath('/nos-actions')" class="navbar__link">
            {{ $t('nav.actions') }} <span class="chevron">▾</span>
          </NuxtLink>
          <div class="navbar__dropdown" :class="{ visible: activeMenu === 'actions' }">
            <NuxtLink :to="localePath('/nos-actions/activites')">{{ $t('nav.actions_activities') }}</NuxtLink>
            <NuxtLink :to="localePath('/nos-actions/programmes')">{{ $t('nav.actions_programs') }}</NuxtLink>
            <NuxtLink :to="localePath('/nos-actions/campagnes')">{{ $t('nav.actions_campaigns') }}</NuxtLink>
            <NuxtLink :to="localePath('/nos-actions/projets')">{{ $t('nav.actions_projects') }}</NuxtLink>
          </div>
        </div>
        <div class="navbar__item" @mouseenter="activeMenu = 'ressources'" @mouseleave="activeMenu = null">
          <NuxtLink :to="localePath('/ressources')" class="navbar__link">
            {{ $t('nav.resources') }} <span class="chevron">▾</span>
          </NuxtLink>
          <div class="navbar__dropdown" :class="{ visible: activeMenu === 'ressources' }">
            <NuxtLink :to="localePath('/ressources/actualites')">{{ $t('nav.resources_news') }}</NuxtLink>
            <NuxtLink :to="localePath('/ressources/documents')">{{ $t('nav.resources_docs') }}</NuxtLink>
            <NuxtLink :to="localePath('/ressources/multimedia')">{{ $t('nav.resources_media') }}</NuxtLink>
          </div>
        </div>
        <NuxtLink :to="localePath('/alrei')" class="navbar__link">{{ $t('nav.alrei') }}</NuxtLink>
      </nav>

      <div class="navbar__actions">
        <!-- Elements moved to navbar__top -->
      </div>

      <button class="navbar__burger" @click="menuOpen = !menuOpen" aria-label="Menu">
        <span></span><span></span><span></span>
      </button>
    </div>

    <!-- Mobile Menu Overlay -->
    <div class="navbar__mobile" :class="{ open: menuOpen }">
      <NuxtLink :to="localePath('/a-propos')" @click="menuOpen = false">{{ $t('nav.about') }}</NuxtLink>
      <NuxtLink :to="localePath('/nos-actions')" @click="menuOpen = false">{{ $t('nav.actions') }}</NuxtLink>
      <NuxtLink :to="localePath('/ressources')" @click="menuOpen = false">{{ $t('nav.resources') }}</NuxtLink>
      <NuxtLink :to="localePath('/alrei')" @click="menuOpen = false">{{ $t('nav.alrei') }}</NuxtLink>
      <NuxtLink :to="localePath('/soutenir')" class="btn btn--primary" @click="menuOpen = false">{{ $t('nav.support') }}</NuxtLink>
    </div>
  </header>
</template>

<style scoped>
.chevron {
  font-size: 0.7rem;
  opacity: 0.5;
}

.navbar__mobile {
  position: fixed;
  top: 90px;
  left: 0;
  width: 100%;
  background: white;
  display: flex;
  flex-direction: column;
  padding: 2rem;
  gap: 1.5rem;
  transform: translateY(-100%);
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
  z-index: 999;
  box-shadow: 0 10px 20px rgba(0,0,0,0.1);
}

.navbar__mobile.open {
  transform: translateY(0);
  opacity: 1;
  visibility: visible;
}

.navbar {
  display: flex;
  flex-direction: column;
  height: auto;
}

.navbar__top {
  background: var(--color-secondary);
  color: white;
  padding: 0.5rem 0;
  font-size: 0.8rem;
}

.navbar__top-inner {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  gap: 2rem;
}

.navbar__inner {
  height: 90px;
}

.btn--xs {
  padding: 0.4rem 1rem;
  font-size: 0.7rem;
}

.navbar__lang button {
  background: none;
  border: none;
  font-family: inherit;
  font-weight: 700;
  cursor: pointer;
  color: rgba(255,255,255,0.6);
  padding: 0 0.3rem;
  transition: color 0.3s ease;
}

.navbar__lang button.active {
  color: var(--color-white);
}

.navbar__lang button:hover {
  color: var(--color-primary);
}

.navbar__mobile a {
  font-weight: 700;
  text-transform: uppercase;
  font-size: 1rem;
}
</style>
