<script setup>
import { ref } from 'vue';

const educacion = ref([
    { 
        id: 1, 
        anio: "2024", 
        titulo: "Técnicatura Universitaria en Programación UTN FSRS", 
        descripcion: "Operación y programación de computadoras, desarrollo de programas en distintos lenguajes, análisis y control de sistemas informáticos." 
    },
    { 
        id: 2, 
        anio: "2023", 
        titulo: "Desarrollador Full Stack", 
        descripcion: "Trabajé en XYZ Tech, donde diseñé y desarrollé aplicaciones web completas utilizando tecnologías como Node.js, React y MongoDB." 
    },
    { 
        id: 3, 
        anio: "2022", 
        titulo: "Internship en Desarrollo Web", 
        descripcion: "Realicé una pasantía en ABC Solutions, contribuyendo en la creación de interfaces de usuario y optimización de sitios web." 
    },
    { 
        id: 4, 
        anio: "2021", 
        titulo: "Proyecto Personal - Aplicación de Gestión de Tareas", 
        descripcion: "" 
    }
]);
</script>

<template>
  <section class="timeline-container">
    <!--titulo-->
    <h3 class="section-title">Educación - Cursos</h3>
    <div class="timeline">
      <!-- Iterar sobre los elementos de la línea de tiempo -->
      <div 
        v-for="(item, index) in educacion" :key="item.id" class="timeline-item" :class="{ 'left': index % 2 === 0, 'right': index % 2 !== 0 }">
        <!-- Contenido de cada elemento -->
        <div class="timeline-content">
          <div class="timeline-year">{{ item.anio }}</div>
          <div class="timeline-title">{{ item.titulo }}</div>
          <!-- Mostrar descripción solo si existe -->
          <p v-if="item.descripcion" class="timeline-description">{{ item.descripcion }}</p>
          <!-- Mostrar botón "Saber más" solo si hay descripción -->
          <a v-if="item.descripcion" href="#" class="timeline-button" target="_blank" rel="noopener noreferrer">Saber más</a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Contenedor principal */
.timeline-container {
  padding: 50px 20px;
  font-family: Arial, sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* Título de la sección */
.section-title {
  font-size: 1.6rem;
  padding-bottom: 2rem;
}

/* Contenedor de la línea de tiempo */
.timeline {
  position: relative;
  width: 90%;
  max-width: 1200px;
  border-radius: 50%;
}

/* La línea central */
.timeline::after {
  content: '';
  position: absolute;
  width: 4px;
  background-color: #007bff;
  top: 0;
  bottom: 0;
  left: 50%;
  margin-left: -2px;
}

/* Elemento individual de la línea de tiempo */
.timeline-item {
  padding: 10px 0;
  position: relative;
  width: 50%;
  border: 2px solid #007bff;
  border-radius: 10px;
  background-color: rgb(28 , 41, 52);
}

/* Alineación de los elementos */
.left {
  left: 0;
  padding-right: 10px;
}

.right {
  left: 50%;
  padding-left: 10px;
}

/* Posición de los círculos para cada lado */
.left::after {
  right: -8px;
}

.right::after {
  left: -8px;
}

/* Contenido de la caja */
.timeline-content {
  padding: 20px;
  border-radius: 6px;
  position: relative;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
}

/* Estilo del texto */
.timeline-year {
  font-size: 1rem;
  font-weight: bold;
}

.timeline-title {
  font-size: 1.2rem;
  font-weight: bold;
  padding-bottom: 5px;
}

.timeline-description {
  font-size: 0.9rem;
  line-height: 1.4;
  margin-bottom: 15px;
}

.timeline-button {
  display: inline-block;
  color: white;
  padding: 8px 15px;
  text-decoration: none;
  border-radius: 4px;
  font-size: 0.8rem;
  transition: background-color 0.3s;
}

.timeline-button:hover {
  background-color: rgba(0, 0, 0, 0.4);
}
</style>
