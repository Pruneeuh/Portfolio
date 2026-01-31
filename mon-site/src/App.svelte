<script>
  import Router from 'svelte-spa-router'
  import Home from './Home.svelte'
  import EngineeringCourse from './Engineering_course.svelte'
  import CivilEngagment from './Civil_engagment.svelte'
  import Experience from './Experience.svelte';
  import { onMount, onDestroy } from 'svelte';

  const routes = {
    '/': Home,
    '/engineering': EngineeringCourse,
    '/civil-engagment': CivilEngagment,
    '/experience': Experience,
  } 

  // variable qui indique si l'utilisateur a scrollé
  let scrolled = false;

  const handleScroll = () => {
    scrolled = window.scrollY > 0;
  };

  onMount(() => {
    handleScroll(); // état initial
    window.addEventListener('scroll', handleScroll, { passive: true });
  });

  onDestroy(() => {
    window.removeEventListener('scroll', handleScroll);
  });
</script>

<div class="main-layout">
  <!-- Ajout d'un class directive Svelte pour appliquer .scrolled quand scrolled=true -->
  <nav class="navbar" class:scrolled={scrolled}>
    <a href="#/" class="nav-link">Accueil</a>
    <a href="#/engineering" class="nav-link">Engineering course</a>
    <a href="#/civil-engagment" class="nav-link">Civil Engagment</a>
    <a href="#/experience" class="nav-link">Experience</a>
  </nav>
  <Router {routes} />
</div>

<style>
  
.main-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.navbar {
  display: flex;
  justify-content: center; /* ou flex-start si tu veux aligner à gauche */
  gap: 2em;
  padding: 1em 0;
  position: sticky;
  top: 0;
  z-index: 10;
}

/* état par défaut : transparent */
.navbar {
  background: transparent;
  transition: background-color 240ms ease, box-shadow 240ms ease;
}

/* quand on a scrollé : fond blanc et légère ombre */
.navbar.scrolled {
  background-color: #ffffff;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
}

/* Optionnel : s'assurer que les liens restent lisibles */
.nav-link {
  color: inherit;
  text-decoration: none;
}
</style>
