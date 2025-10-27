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

const hasText = (desc) => desc && desc.trim().length > 0;
</script>

<template>
    <section class="timeline-container" aria-labelledby="timeline-title">
        <h3 id="timeline-title" class="section-title">Educación - Cursos 🎓</h3>
        <ul class="timeline">
            <li 
                v-for="(item, index) in educacion" 
                :key="item.id" 
                class="timeline-item" 
                :class="{ 'left': index % 2 === 0, 'right': index % 2 !== 0 }"
            >
                <div class="timeline-content">
                    <div class="timeline-year">{{ item.anio }}</div>
                    <div class="timeline-title">{{ item.titulo }}</div>
                    
                    <p v-if="hasText(item.descripcion)" class="timeline-description">{{ item.descripcion }}</p>
                </div>
            </li>
        </ul>
    </section>
</template>

<style scoped>
/* ---------------------------------------------------- */
/* --- VARIABLES Y ESTRUCTURA BASE --- */
/* ---------------------------------------------------- */

.timeline-container {
    --primary-color: #007bff;
    --bg-item-color: rgb(28 , 41, 52);
    --line-width: 4px;
    --dot-size: 14px;
    --gap-to-line: 60px; /* 🚀 MEJORA CLAVE: Aumentado a 60px para mayor separación */
    --dot-offset: 15px; /* Ajuste del punto de conexión */
    
    padding: 50px 20px;
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    color: white;
}

.section-title {
    font-size: 1.6rem;
    padding-bottom: 2rem;
    color: var(--primary-color);
    text-align: center;
}

.timeline {
    position: relative;
    width: 90%;
    max-width: 1200px;
    padding: 0;
    list-style: none;
}

/* La línea central */
.timeline::after {
    content: '';
    position: absolute;
    width: var(--line-width);
    background-color: var(--primary-color);
    top: 0;
    bottom: 0;
    left: 50%;
    margin-left: calc(var(--line-width) / -2); 
    z-index: 0;
}

/* ---------------------------------------------------- */
/* --- ELEMENTOS DE LA LÍNEA DE TIEMPO (TARJETAS) --- */
/* ---------------------------------------------------- */

.timeline-item {
    padding: 10px 0;
    position: relative;
    width: 50%;
    z-index: 1; 
    border: 2px solid var(--primary-color);
    border-radius: 10px;
    background-color: var(--bg-item-color);
    margin-bottom: 30px;
}

/* Círculo del evento (punto de conexión) */
.timeline-item::before {
    content: '';
    position: absolute;
    width: var(--dot-size);
    height: var(--dot-size);
    background-color: white;
    border: 3px solid var(--primary-color);
    top: 50%;
    transform: translateY(-50%);
    border-radius: 50%;
    z-index: 10;
}

/* Contenido de la caja */
.timeline-content {
    padding: 20px;
    border-radius: 6px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
}

/* 🚀 MEJORA: Aplicamos el gap (separación) */
.left {
    left: 0;
    padding-right: var(--gap-to-line); 
}

.right {
    left: 50%;
    padding-left: var(--gap-to-line); 
}

/* Posición de los círculos (puntos de conexión) */
/* El punto se ubica dentro del espacio de separación (gap) */
.left::before {
    right: var(--dot-offset); 
}

.right::before {
    left: var(--dot-offset);
}

/* --- ESTILOS DE TEXTO --- */

.timeline-year {
    font-size: 1rem;
    font-weight: bold;
    color: var(--primary-color);
}
.timeline-title {
    font-size: 1.2rem;
    font-weight: bold;
    padding-bottom: 5px;
}
.timeline-description {
    font-size: 0.9rem;
    line-height: 1.4;
    margin-bottom: 0; 
}

/* 📱 Responsive para móviles (una columna) */
@media screen and (max-width: 768px) {
    /* Mover la línea central a la izquierda */
    .timeline::after {
        left: 20px;
        margin-left: 0;
    }

    .timeline-item {
        width: 100%;
        left: 0 !important;
        /* Usar un padding fijo en móvil */
        padding-left: 50px; 
        padding-right: 10px;
    }

    /* Posicionar el punto del evento cerca de la nueva línea */
    .timeline-item::before {
        left: 14px; 
        right: auto !important;
        transform: translateY(-50%);
    }
}
</style>