<script setup>
const localePath = useLocalePath()
</script>

<template>
  <footer class="footer">
    <div class="container footer__grid">
      <div class="footer__brand">
        <NuxtLink to="/">
          <img src="https://ituc-africa.org/IMG/logo/siteon0.jpg" alt="CSI-Afrique" class="footer__logo" />
        </NuxtLink>
        <p class="footer__desc">
          {{ $t('footer.description') }}
        </p>
        <address class="footer__address">
          Route Internationale d'Atakpamé<br>
          Centre FOPADESC Agoè-Nyivé<br>
          BP 4401, Lomé - TOGO<br>
          Email: info@ituc-africa.org
        </address>
      </div>

      <div class="footer__col">
        <h4 class="footer__col-title">{{ $t('nav.resources') }}</h4>
        <ul class="footer__links">
          <li><NuxtLink to="/communications/declarations">Déclarations</NuxtLink></li>
          <li><NuxtLink to="/communications/discours">Discours</NuxtLink></li>
          <li><NuxtLink to="/communications/communiques">Communiqués</NuxtLink></li>
          <li><NuxtLink to="/communications/petitions">Pétitions</NuxtLink></li>
        </ul>
      </div>

      <div class="footer__col">
        <h4 class="footer__col-title">{{ $t('nav.actions') }}</h4>
        <ul class="footer__links">
          <li><NuxtLink to="/actions/nys">NYS</NuxtLink></li>
          <li><NuxtLink to="/actions/congres">Congrès</NuxtLink></li>
          <li><NuxtLink to="/alrei">ALREI</NuxtLink></li>
          <li><NuxtLink to="/nos-actions/activites">Activités</NuxtLink></li>
        </ul>
      </div>

      <div class="footer__col">
        <h4 class="footer__col-title">{{ $t('nav.actions_campaigns') }}</h4>
        <ul class="footer__links">
          <li><NuxtLink to="/campagnes/dette">Dette</NuxtLink></li>
          <li><NuxtLink to="/campagnes/migration">Migration</NuxtLink></li>
          <li><NuxtLink to="/campagnes/climat">Climat</NuxtLink></li>
          <li><NuxtLink to="/campagnes/genre">Genre</NuxtLink></li>
        </ul>
      </div>
    </div>

    <div class="footer__bottom">
      <div class="container footer__bottom-inner">
        <span>© {{ new Date().getFullYear() }} ITUC-Africa / CSI-Afrique. {{ $t('footer.rights') }}</span>
        <div class="footer__legal">
          <NuxtLink :to="localePath('/mentions-legales')">{{ $t('footer.legal') }}</NuxtLink>
          <NuxtLink :to="localePath('/confidentialite')">{{ $t('footer.privacy') }}</NuxtLink>
        </div>
      </div>
    </div>
  </footer>
</template>
