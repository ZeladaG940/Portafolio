<script setup>
import usb from '../assets/usb-svgrepo-com.svg';
import webPage from '../assets/web-page-material-svgrepo-com.svg';
import baseData from '../assets/web-cloud-server-database-hosting-storage-svgrepo-com.svg';
import Seguridad from '../assets/web-guard-svgrepo-com.svg';  
// Importamos la función 'ref' desde Vue para crear variables reactivas
import { ref } from 'vue';

// Datos básicos del encabezado
const titulo = "Desarrollador Fullstack";
const fecha = "2020 - 2025";

// Creamos una referencia reactiva para la lista de experiencias
const experiencia = ref([
  {
    id: 1,
    src: usb,
    parrafo:
      "Lideré un equipo de 5 personas para un proyecto de casino online con recargas y juegos en tiempo real, logrando un alto nivel de éxito y participación."
  },
  {
    id: 2,
    src: webPage,
    parrafo:
      "Diseñé sitios web personalizables para pequeñas empresas y emprendedores, con interfaces atractivas y completamente responsivas."
  },
  {
    id: 3,
    src: baseData,
    parrafo:
      "Colaboré en el desarrollo de aplicaciones internas en PHP y Laravel, incluyendo reportes automatizados con MySQL y documentación técnica."
  },
  {
    id: 4,
    src: Seguridad,
    parrafo:
      "Administré bases de datos MySQL y MariaDB, realizando copias de seguridad, restauración, optimización de consultas SQL y control de permisos de usuarios."
  }
]);
</script>

<template>
  <!-- Sección principal de experiencia -->
  <section class="experiencia">
    <!-- Encabezado con título y fecha -->
     <h2>Experiencias 🗺️🧠</h2>
    <div class="header">
      <h3>{{ titulo }}</h3>
      <p class="fecha">{{ fecha }}</p>
    </div>

    <!-- Lista de experiencias -->
    <ul class="lista-experiencia">
      <li v-for="exp in experiencia" :key="exp.id" class="item-experiencia">
        <!-- Ícono de la experiencia -->
        <img :src="exp.src" alt="icono" class="icono" />
        <!-- Descripción de la experiencia -->
        <p>{{ exp.parrafo }}</p>
      </li>
    </ul>
  </section>
</template>

<style scoped>
/* === SECCIÓN PRINCIPAL === */
.experiencia {
  font-family: Arial, sans-serif;
  background: rgb(28 , 41, 52);
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  max-width: 1200px;
  margin: 2rem auto;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  border: 2px solid #007bff;
}
.experiencia:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 18px rgba(0, 0, 0, 0.12);
}

/* === CABECERA (TÍTULO Y FECHA) === */
.header {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  border-bottom: 2px solid #007bff;
  margin-bottom: 1.5rem;
  padding-bottom: 0.5rem;
}
/* === LISTA DE EXPERIENCIAS === */
.lista-experiencia {
  list-style: none;
  padding: 0;
  margin: 0;
}
.item-experiencia {
  border: 2px solid #007bff;
  display: flex;
  align-items: flex-start;
  background: rgb(28 , 41, 52);
  border-radius: 8px;
  padding: 1rem 1.2rem;
  margin-bottom: 1rem;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
  transition: background 0.2s ease, transform 0.2s ease;
}
.item-experiencia:hover {
  transform: translateY(-3px);
}
.icono {
  width: 35px;
  height: 35px;
  margin-right: 1rem;
  flex-shrink: 0;
  background-color: aliceblue;
  border-radius: 10px;
  border: 2px solid seashell;
}
.item-experiencia p {
  font-size: 1rem;
  line-height: 1.5;
  margin: 0;
}
/* === RESPONSIVE === */
@media (max-width: 600px) {
  .experiencia {
    padding: 1.2rem;
  }
  .header {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.3rem;
  }
  .item-experiencia {
    flex-direction: column;
    text-align: left;
  }
  .icono {
    margin-bottom: 0.5rem;
  }
  h2{
    font-size: 2rem;
    font-weight: 900;
  }
}
</style>

