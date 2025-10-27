<script setup>
    import linkedin from "/src/assets/linkedin-161-svgrepo-com.svg";
    import instagram from "/src/assets/instagram-167-svgrepo-com.svg";
    import github from "/src/assets/github-142-svgrepo-com.svg";
    import curriculum from "/src/assets/curriculum-vitae-resume-svgrepo-com.svg";
    import foto from "@/assets/img/micha.jpg";
    import { ref } from "vue";
    //variables
    const titulo = "Orlando zelada"
    const titulo2 = "Tecnico universitario en Programamcion - UTN";
    const descripcion = "Hola bienvenido a mi protafolio de proyectos. Soy un desarrollador web con experiencia en aplicaciones web y moviles.";
    const residencia = "Tupungato, Mendoza, Argentina"

    //lista de redes
    const redesSociales = ref([
    {id: 1, nombre: "linkedin", src: linkedin, url : "https://www.linkedin.com/in/orlando-zeladagira-2b7bb036a/"},
    {id: 2, nombre: "instagram", src: instagram, url : "https://www.instagram.com/orlando.zeladagira.3/"},
    {id: 3, nombre: "github", src: github, url : "https://github.com/ZeladaG940"},
    {id: 4, nombre: "curriculon ", src: curriculum, url : ""}
    ])
    const numeroTelefono = "Mi telefono persona: +54 2622-292671"
</script>

<template>
    <section class="datos-personales">
        <div class="card">

            <!--presentacion-->
            <h1>{{ titulo }}</h1>
            <img :src=foto alt="mi foto" class="perfil">
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
    .perfil {
        border-radius: 50%;
        width: 200px;
        height: 200px;
        object-fit: cover;
        margin: 1rem 0;
        border: 2px solid #007bff;
    }
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