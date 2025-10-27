<script setup>
import { ref } from 'vue';

// Lista de intereses
const intereses = ref([
  {
    id: 1,
    texto: "Desarrollo de software de código abierto: contribuyo a proyectos de código abierto en plataformas como GitHub, colaborando con otros desarrolladores para mejorar herramientas y librerías populares."
  },
  {
    id: 2,
    texto: "Deportes al aire libre: disfruto actividades como el senderismo, ciclismo y la escalada, que me permiten conectar con la naturaleza y mantenerme activo físicamente."
  },
  {
    id: 3,
    texto: "Tecnología de innovación: me apasiona explorar las últimas tendencias en tecnología, como la inteligencia artificial, la realidad aumentada y el internet de las cosas."
  },
  {
    id: 4,
    texto: "Fotografía digital: me gusta capturar momentos y paisajes a través de la fotografía, experimentando con diferentes técnicas y estilos para mejorar mis habilidades artísticas."
  }
]);

const inter = "Mis Intereses";
</script>

<template>
  <section class="intereses-seccion">
    <div class="contenedor">
      <h3>{{ inter }}</h3>
      <ul class="contenedor-lista">
        <!-- Iteramos sobre los intereses y mostramos cada uno -->
        <li v-for="interes in intereses" :key="interes.id" class="item">
          <p>{{ interes.texto }}</p>
        </li>
      </ul>
    </div>
  </section>
</template>

<style scoped>
  /* Contenedor principal */
  .intereses-seccion {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 3rem 1rem;
    border-radius: 15px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  }

  /* Título */
  h3 {
    font-size: 2rem;
    text-align: center;
    margin-top: 2rem;
    margin-right: 5rem;
  }

  /* Estilos para la lista */
  .contenedor-lista {
    list-style-type: none;
    padding: 0;
    margin: 0;
  }

  /* Estilo para los items (intereses) */
  .item {
    background-color: transparent; /* Fondo transparente, no tarjetas */
    color: #fff; /* Texto blanco */
    font-size: 1.2rem;
    padding: 1rem;
    line-height: 1.6;
  }

  /* Estilo del texto dentro de los items */
  .contenedor-lista p {
    text-align: center;
    font-size: 1.2rem;
    padding-right: 5rem;
  }

  /* Adaptabilidad para dispositivos móviles */
  @media (max-width: 768px) {
    .contenedor-lista {
      padding: 1rem;
    }

    .item {
      font-size: 1rem;
      padding: 0.8rem;
    }
  }
</style>
