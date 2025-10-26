<script setup>
import { ref } from 'vue';

const lengPro = ref([
    {id: 1, nombre: "Javascript: ", nivel: "Avanzado", src: "/src/assets/javascript-16-svgrepo-com.svg"},
    {id: 2, nombre: "Java: ", nivel: "Intermedio", src: "/src/assets/java-16-svgrepo-com.svg"},
    {id: 3, nombre: "Python: ", nivel: "Avanzado", src: "/src/assets/python-svgrepo-com.svg"},
    {id: 4, nombre: "Html/Css: ", nivel: "Avanzado", src: "/src/assets/html-124-svgrepo-com.svg"},
    {id: 5, nombre: "Php: ", nivel: "intermedio", src: "/src/assets/php01-svgrepo-com.svg"}
]);

const baseDatos = ref([
    {id: 1, nombre: "MySQL: ", nivel: "Avanzado", src: "/src/assets/mysql-svgrepo-com.svg"},
    {id: 2, nombre: "MongoDB: ", nivel: "intermedio", src: "/src/assets/mongodb-svgrepo-com.svg"},
    {id: 3, nombre: "PostgreSQL: ", nivel: "Básico", src: "/src/assets/postgresql-svgrepo-com.svg"}
]);

const frameyork = ref([
    {id: 1, nombre: "Vue.js: ", nivel: "Avanzado", src: "/src/assets/vue-16-svgrepo-com.svg"},
    {id: 2, nombre: "React: ", nivel: "Intermedio", src: "/src/assets/react-16-svgrepo-com.svg"},
    {id: 3, nombre: "Node.js: ", nivel: "Intermedio", src: "/src/assets/node-16-svgrepo-com.svg"},
    {id: 4, nombre: "Express.js: ", nivel: "Intermedio", src: "/src/assets/express-svgrepo-com.svg"}
]);

const herrami = ref([
    {id: 1, nombre: "Git: ", nivel: "Avanzado", src: "/src/assets/git-merge-svgrepo-com.svg"},
    {id: 2, nombre: "GitHub: ", nivel: "Avanzado", src: "/src/assets/github-142-svgrepo-com.svg"},
    {id: 3, nombre: "VS Code: ", nivel: "Avanzado", src: "/src/assets/vs-code-logo-microsoft-svgrepo-com.svg"},
    {id: 4, nombre: "Figma: ", nivel: "Intermedio", src: "/src/assets/figma-svgrepo-com.svg"}
]);

const titulo = "Habilidades";
const lang = "Lenguajes de Programación";
const frame = "Frameworks y Librerías";
const herra = "Herramientas de Desarrollo";
const base = "Bases de Datos";
</script>

<template>
    <section class="principal">
        <div class="targetaLenguajes">
            <h2>{{ titulo }}</h2>
            <h3>{{ lang }}</h3>
            <ul class="objetos">
                <li v-for="leng in lengPro" :key="leng.id">
                    <div class="cuadros">
                        <img :src="leng.src" alt="imagenes">
                        <p>{{ leng.nombre }} {{ leng.nivel }}</p>
                    </div>
                </li>
            </ul>
            <h3>{{ frame }}</h3>
            <ul class="objetos">
                <li v-for="framew in frameyork" :key="framew.id">
                    <div class="cuadros">
                        <img :src="framew.src" alt="imagenes">
                        <p>{{ framew.nombre }} {{ framew.nivel }}</p>
                    </div>
                </li>
            </ul>
            <h3>{{ base }}</h3>
            <ul class="objetos">
                <li v-for="baseD in baseDatos" :key="baseD.id">
                    <div class="cuadros">
                        <img :src="baseD.src" alt="imagenes">
                        <p>{{ baseD.nombre }} {{ baseD.nivel }}</p>
                    </div>
                </li>
            </ul>
            <h3>{{ herra }}</h3>
            <ul class="objetos">
                <li v-for="herra in herrami" :key="herra.id">
                    <div class="cuadros">
                        <img :src="herra.src" alt="imagenes">
                        <p>{{ herra.nombre }} {{ herra.nivel }}</p>
                    </div>
                </li>
            </ul>
        </div>
    </section>
</template>

<style scoped>
    /* Contenedor principal */
    .principal {
        width: 1200px;
        height: auto;
        padding-top: 2rem;
    }

    /* Título */
    h2, h3 {
        text-align: center;
        font-size: 23px;
    }

    /* Lista de elementos */
    .objetos {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 2rem;
        flex-wrap: wrap; /* Hace que los elementos se acomoden cuando la pantalla es pequeña */
        list-style: none;
        padding: 20px 0;
    }

    /* Estilo de cada tarjeta */
    .cuadros {
        display: flex;
        justify-content: center;
        align-items: center;
        border: 2px solid #007bff;
        border-radius: 10px;
        padding: 10px;
        background-color: rgb(38, 56, 71); /* Fondo oscuro para las tarjetas */
        width: 11rem;
        height: 3rem;
        transition: transform 0.2s ease;
    }

    /* Hover para las tarjetas */
    .cuadros:hover {
        transform: scale(1.05);
    }

    /* Estilo de la imagen */
    .cuadros img {
        width: 2.5rem;
        height: 2.5rem;
        border-radius: 50%;
        border: 2px solid #ffffff;
        background-color: aliceblue;
    }

    /* Estilo del texto */
    .cuadros p {
        font-weight: 600;
        text-align: center;
        padding: 2px;
    }
    .targetaLenguajes {
        background-color: rgb(28 , 41, 52);
        border: 2px solid #007bff;
        border-radius: 10px;
        width: 1200px;
        height: auto;
    }
</style>
