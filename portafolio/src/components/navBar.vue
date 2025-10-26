<template>
    <header>
        <!--Barra de navegacion-->
        <nav class="navbar">
            <div class="navbar-menu">
                <!--v-for = nav es cada objeto de la variable navegacion  //key="nav.nombre = es un id para cada objeto"-->
                <ul>
                    <a v-for="nav in navegacion" :key="nav.id" :href="nav.enlace" class="nav-item">{{ nav.nombre }}</a>
                </ul>
            </div>
        </nav>
    </header>
</template>

<!------------------------------------------------------------------------------------------------------->
<script setup>
    import { ref } from 'vue';
    const navegacion = ref([
        {id:1, nombre: "Educacion", enlace: "#educacion"},
        {id:2, nombre: "Experiencia", enlace: "#experiencia"},
        {id:3, nombre: "Proyectos", enlace: "#proyectos"},
        {id:4, nombre: "Habilidades", enlace: "#habilidades"},
    ])
</script>
<!------------------------------------------------------------------------------------------------------->

<style scoped>
    .navbar{
        background-color: var(--vt-c-indigo);
        color: #fff;
        padding: 0.5rem 1rem;
        align-items: center;
    }
    .navbar-menu{
        display: flex;
        justify-content: flex-end;
    }

    .nav-item{
        text-decoration: none;
        margin-right: 1rem;
        border: 1px solid rgb(53, 49, 49);;
        border-radius: 5px;
        /*elimina el subrayado de los enlaces y elemtos con clase "green"*/
        text-decoration: none;
        /*añade una transicion suabe para los estilos */
        position: relative;
        transition: transform 0.2s ease;
        /*añade padign al rededro del contenido */
        padding: 5px;
        display: inline-block; 
    }
    .nav-item:hover{
        transform: translateY(-3px);
        background-color: rgba(0, 0, 0, 0.1); 
    }
    /*responsivo */
    @media (max-width: 768px){
        .navbar-menu {
            display: flex;
            justify-content: flex-end;
            width: 100%;
        }
    }
</style>