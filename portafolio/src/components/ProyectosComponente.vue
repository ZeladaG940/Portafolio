<script setup>
import { ref } from 'vue';
import descubre from '/src/assets/img/descubre-los-7-tipos-de-sitios-web-mas-populares.jpg';
import pagina from '/src/assets/img/pagina-web.webp';
import web from '/src/assets/img/por-que-tener-una-pagina-web.png-601x401.webp';
import tipos from '/src/assets/img/tipos-clasificacion-paginas-web.png.webp';

//arreglo de proyectos
const Educacion = ref([]);
Educacion.value = [
  {
    id: 1,
    fecha: 'Blog Personal con Node.js',
    stack: 'HTML, CSS, JavaScript, Node.js, Express, MongoDB',
    descripcion:
      'Creación de un blog personal con registro e inicio de sesión, publicación de artículos y comentarios. Enfocado en aprender la estructura cliente-servidor y el manejo de bases de datos NoSQL.',
    enlace: '#',
    src: descubre,
    link: "https://github.com/ZeladaG940?tab=repositories"
  },
  {
    id: 2,
    fecha: 'Tienda Online (E-commerce)',
    stack: 'React, Node.js, Express, MongoDB',
    descripcion:
      'Desarrollo de una aplicación de comercio electrónico con carrito de compras, administración de productos y simulación de pagos. Implementación completa de un API RESTful.',
    enlace: '#',
    src: pagina,
    link: "https://github.com/ZeladaG940?tab=repositories"
  },
  {
    id: 3,
    fecha: 'Gestor de Tareas con JWT y React Hooks',
    stack: 'React, Node.js, Express, PostgreSQL, JWT',
    descripcion:
      'Aplicación que permite crear, editar y eliminar tareas, con autenticación basada en tokens JWT. Se refuerzan conceptos de seguridad y manejo de sesiones.',
    enlace: '#',
    src: web,
    link: "https://github.com/ZeladaG940?tab=repositories"
  },
  {
    id: 4,
    fecha: 'Dashboard Analítico con GraphQL',
    stack: 'Next.js, Apollo GraphQL, Node.js, Prisma, PostgreSQL',
    descripcion:
      'Creación de un panel de análisis de datos con consultas dinámicas mediante GraphQL. Visualización de datos en tiempo real y filtrado avanzado con gráficos interactivos.',
    enlace: '#',
    src: tipos,
    link: "https://github.com/ZeladaG940?tab=repositories"
  },
];
const boton = "Ver proyecto";
const github = "Ver en GitHub";
</script>

<template>
  <section class="educacion">
    <h2>Proyectos 🛠️🚀</h2>
    <!-- lista de proyectos -->
    <ul class="lista-proyectos">

      <!--lista de objetos-->
      <li v-for="edu in Educacion" :key="edu.id" class="item">

        <!--objetos por separados con un div-->
        <div class="div">
          <a :href="edu.link" target="_blank" ref="noopener noreferrer"><img :src="edu.src" alt="imagen"></img></a>
          <!--titulo-->
          <h3><a :href="edu.enlace">{{ edu.fecha }}</a></h3>
          <!--descripcion-->
          <p><strong>Stack:</strong> {{ edu.stack }}</p>
          <p>{{ edu.descripcion }}</p>
          <!--botones-->
          <div class="buton">
            <button><a href="#">{{ boton }}</a></button>
            <button><a :href="edu.link">{{ github }}</a></button>
          </div>
      </div>
      </li>
    </ul>
  </section>
</template>

<style scoped>
/* Estilos principales */
.educacion {
  background-color: rgb(28 , 41, 52);
  padding-top: 10px;
  max-width: 1200px;
  height: auto;
  border: 2px solid #007bff;
  border-radius: 15px;
  transition: transform 0.2s ease;
}

.educacion:hover {
  transform: translateY(-3px);
}

/* Contenedor de la lista de proyectos */
.lista-proyectos {
  list-style-type: none;
  display: flex;
  flex-wrap: wrap; /* Permite que los items se envuelvan en pantallas pequeñas */
  justify-content: space-around;
  padding: 15px;
  gap: 20px; /* Espaciado entre los elementos */
}

/* Cada item de la lista */
.div {
  max-width: 250px;
  width: 100%; /* Asegura que el div ocupe el 100% de su contenedor en pantallas pequeñas */
  height: auto;
  border: 2px solid #007bff;
  border-radius: 10px;
  text-align: center;
  font-size: 14px;
  padding-bottom: 10px;
  transition: transform 0.2s ease;
}

.div:hover {
  transform: translateY(-3px);
}

/* Imágenes responsivas */
img {
  width: 100%; /* Hace que la imagen ocupe todo el ancho disponible */
  height: 150px;
  padding-top: 5px;
  border-radius: 10px;
}

/* Títulos y texto */
h3 {
  font-size: 16px;
  padding: 10px;
  text-align: center;
}

p {
  padding: 5px 10px;
  text-align: center;
}

/* Estilos para los botones */
.buton {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5px;
}

.buton button {
  background-color: rgb(71, 50, 233);
  border: 0px solid;
  border-radius: 5px;
  width: 14.5rem;
  height: 1.8rem;
  font-size: 14px;
  transition: transform 0.2s ease;
}

.buton button:hover {
  transform: translateY(-3px);
  background-color: rgba(0, 0, 0, 0.1);
}
h2 {
  padding: 10px 10px 10px 10px;
  text-align: center;
}

/* Responsividad: Cambiar la disposición de los elementos según el tamaño de la pantalla */
@media (max-width: 1024px) {
  .div {
    max-width: 100%; /* En pantallas medianas, los elementos ocupan todo el ancho */
  }

  img {
    height: auto; /* Hacer que la altura de la imagen sea automática */
  }

  .buton button {
    width: 100%; /* Botones más anchos en pantallas pequeñas */
  }
}

/* Pantalla de móviles */
@media (max-width: 768px) {
  .lista-proyectos {
    flex-direction: column; /* En pantallas móviles, los elementos se apilan uno debajo del otro */
    align-items: center; /* Alinear los elementos al centro */
  }

  .div {
    max-width: 90%; /* Reducir el tamaño de los divs */
  }

  .buton button {
    width: 100%; /* Hacer los botones de ancho completo */
  }
}
</style>
