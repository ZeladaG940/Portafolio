
<script setup>
  import ExperienciaFullStak from './components/ExperienciaFullStak.vue';
  import Proyectos from './components/ProyectosComponente.vue';
  import navBar from './components/navBar.vue';
  import DatosPersonales from './components/DatosPersonales.vue';
  import EducacionCursos from './components/EducacionCursos.vue';
  import ProyectosComponente from './components/ProyectosComponente.vue';
  import HabilidadesComponente from './components/HabilidadesComponente.vue';
  import InterecesComponente from './components/InterecesComponente.vue';
</script>

<template>
  <header>
    <navBar/>
    <DatosPersonales/>
  </header>
  <main>
    <section id="educacion"><EducacionCursos/></section>

    <section id="experiencia"><ExperienciaFullStak/></section>

    <section id="proyectos"><ProyectosComponente/></section>

    <section id="habilidades"><HabilidadesComponente/></section>

    <section id="intereses"><InterecesComponente/></section>
  </main>
</template>

<style scoped>
  section{
    text-align: center;
  }
</style>
