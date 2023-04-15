<template>
    <div>
        <Navbar />
        <main>
            <slot></slot>
        </main>
        <!-- <footer>&copy; Brayan - {{ currentYear }}</footer> -->
    </div>
</template>

<script setup>

//utilizar muchas propiedades, permite ingresar al head de la aplicacion
useHead({
    link: [
        {
            rel: "stylesheet",
            href: "/assets/css/style.css",
        },
        {
            rel: "stylesheet",
            href: "https://fonts.googleapis.com/icon?family=Material+Icons"
        },
        {
            rel:"stylesheet",
            href:"/assets/fonts/san-serif-pro.css"
        },
        {
            rel:"stylesheet",
            href:"/assets/fonts/MWF-MDL2.css"
        }
        
        
    ]
})

// const currentYear = new Date().getUTCFullYear();

</script>