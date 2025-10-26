<script setup>
    import {ref} from "vue";

    //variables
    const titulo = "Orlando zelada"
    const titulo2 = "Tecnico universitario en Programamcion - UTN";
    const descripcion = "Hola bienvenido a mi protafolio de proyectos. Soy un desarrollador web con experiencia en aplicaciones web y moviles.";
    const residencia = "Tupungato, Mendoza, Argentina"

    //lista de redes
    const redesSociales = ref([
    {id: 1, nombre: "linkedin", src: "/src/assets/linkedin-161-svgrepo-com.svg", url : "https://www.linkedin.com/in/orlando-zeladagira-2b7bb036a/"},
    {id: 2, nombre: "instagram", src: "/src/assets/instagram-167-svgrepo-com.svg", url : "https://www.instagram.com/orlando.zeladagira.3/"},
    {id: 3, nombre: "github", src: "/src/assets/github-142-svgrepo-com.svg", url : "https://github.com/ZeladaG940"},
    {id: 4, nombre: "curriculon ", src: "/src/assets/curriculum-vitae-resume-svgrepo-com.svg", url : ""}
    ])
    const numeroTelefono = "Mi telefono persona: +54 2622-292671"
</script>

<template>
    <section class="datos-personales">
        <div class="card">

            <!--presentacion-->
            <h1>{{ titulo }}</h1>
            <h2>{{ titulo2 }}</h2>
            <p>{{ descripcion }}</p>

            <!--lista de redes sociales-->
            <ul class="container-lista">
                <li v-for="red in redesSociales" :key="red.id">
                    <a :href="red.url" target="_blank" rel="noopener noreferrer"><img class="icon-redsocial" :src="red.src" :alt="red.nombre" width="35rem"></a>
                </li>
            </ul>
            
            <!--contactos-->
            <h3>{{ numeroTelefono }}</h3>
            <h4>{{ residencia }}</h4>
        </div>
    </section>
</template>

<style scoped>
    h1 {
        font-size: 2.5rem;
    }

    p {
        font-size: 1.2rem;
        font-weight: 600;
        margin-bottom: 1rem;
    }

    .card{
        background-color: rgb(28 , 41, 52);
        border-radius: 10px;
        padding: 10px;
        margin: 10px;
        text-align: center;
        border: 2px solid #007bff;
    }

    .container-lista{
        display: flex;
        justify-content: center;
        list-style: none;
        padding: 0;
        margin: 0;
        text-align: center;
    }

    .icon-redsocial{
        align-items: center;
        background-color: aliceblue;
        border-radius: 50%;
        padding: 2px;
        margin: 5px;
        box-shadow: 0 0 5px rgba(95, 124, 205, 0.934);
    }

    .icon-redsocial:hover{
        background-color: rgb(28, 41, 52);
        box-shadow: 0 0 5px rgba(95, 124, 205, 0.934);
    }

    h3 {
        font-size: 1.2rem;
        font-weight: 600;
    }
</style>