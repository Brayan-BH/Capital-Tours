<template>
    <!-- Navbar -->
    <header class="header-page" itemscope="itemscope">
        <div class="head-container">
            <div class="container__item">
                <div class="item__button_menu" ref="button_movil_menu">
                    <nuxt-link  :href="interaction.menu_movil_action" class="item-button-menu__href" @click="menu_movil_click">
                        <div class="item-button-menu__container">
                            <i class="material-icons">{{ interaction.movil_menu_icon }}</i>
                        </div>
                    </nuxt-link >
                </div>
                <nuxt-link  class="item__logo" itemprop="url" href="/">
                    <img class="logo__img" src="/img/logo.png" alt="logo">
                </nuxt-link >
                <div class="item__div">
                    <nuxt-link class="div__text" to="/">
                        <span>Capital Tours</span>
                    </nuxt-link>
                </div>
                <nav id="id-menu" class="item__menu" :class="[interaction.movil_menu_open ? 'open' : '']">
                    <ul class="menu_ul">
                        <li class="ul__li">
                            <nuxt-link to="/" class="li__text">Inicio</nuxt-link>
                        </li>
                        <li class="ul__li">
                            <nuxt-link to="/nosotros" class="li__text">Nosotros</nuxt-link>
                        </li>
                        <li class="ul__li">
                            <nuxt-link to="/equipo" class="li__text">Equipo</nuxt-link>
                        </li>
                        <li class="ul__li">
                            <nuxt-link to="/contactanos" class="li__text">Contáctanos</nuxt-link>
                        </li>
                        <li class="ul__li">
                            <nuxt-link to="/empresas" class="li__text">Empresa</nuxt-link>
                        </li><li class="ul__li">
                            <nuxt-link to="/servicios" class="li__text">Servicios</nuxt-link>
                        </li>
                        <li class="ul__li">
                            <nuxt-link to="/requisitos" class="li__text">Requisitos</nuxt-link>
                        </li>
                    </ul>

                </nav>
                <div class="item__action">
                    <div class="action-container">
                        <!-- <div class="action__whats">
                            <nav class="item__menu">
                                <ul class="menu_ul">
                                    <li class="ul__li">
                                        <div class="li__container">
                                            <button type="button" class="li-container__button">
                                                Servicios
                                            </button>
                                            <ul class="li-container__menu">
                                                <li class="">
                                                    <span class="menu__header">Para Pequeñas Empresas</span>
                                                    <ul class="menu__body">
                                                        <li class="body__item">
                                                            <nuxt-link to="">Contabilidad</nuxt-link >
                                                        </li>
                                                        <li class="body__item">
                                                            <nuxt-link to="">Facturación</nuxt-link >
                                                        </li>
                                                    </ul>
                                                </li>
                                                <li class="">
                                                    <span class="menu__header">Para Mediana Empresa</span>
                                                    <ul class="menu__body">
                                                        <li class="body__item">
                                                            <nuxt-link to="">Contabilidad</nuxt-link >
                                                        </li>
                                                        <li class="body__item">
                                                            <nuxt-link to="">Sucursales</nuxt-link >
                                                        </li>
                                                    </ul>
                                                </li>

                                                <li class="">
                                                    <span class="menu__header">Para grandes empresas</span>
                                                    <ul class="menu__body">
                                                        <li class="body__item">
                                                            <nuxt-link to="">Precios para grandes empresas</nuxt-link >
                                                        </li>
                                                        <li class="body__item">
                                                            <nuxt-link to="">Multi Sucursales</nuxt-link >
                                                        </li>
                                                        <li class="body__item">
                                                            <nuxt-link to="">Contabilidad</nuxt-link >
                                                        </li>
                                                        <li class="body__item">
                                                            <nuxt-link to="">Stock</nuxt-link>
                                                        </li>
                                                    </ul>
                                                </li>
                                            </ul>
                                        </div>
                                    </li>
                                </ul>

                            </nav>
                        </div> -->
                        <div class="action__control">
                            <div class="control__container">
                                <div class="container__text cl-session">
                                    <nuxt-link to="/login" class="li__text">Iniciar Sesión</nuxt-link>
                                </div>
                                <div class="container__icon">
                                    <nuxt-link to="/login" class="material-icons">login</nuxt-link>
                                </div>
                            </div>
                        </div>
                        <div class="action__control">
                            <div class="control__container">
                                <div class="container__text">
                                    <nuxt-link to="/signup" class="li__text">Registrate Ahora</nuxt-link>
                                </div>
                                <div class="container__icon">
                                    <nuxt-link to="/signup" class="material-icons">how_to_reg</nuxt-link>
                                </div>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<script>

export default {
    name: "Navbar",
    mounted() {
        let l = this.$refs.button_movil_menu
        console.log(l.style.display);
    },
    data() {
        return {
            interaction: {
                movil_menu_open: false,
                menu_movil_action: "#id-menu",
                movil_menu_icon: "menu"
            }
        }
    },
    methods: {
        menu_movil_click() {
            this.interaction.movil_menu_open = !this.interaction.movil_menu_open
            if (this.interaction.movil_menu_open) {
                this.interaction.menu_movil_action = "#"
                this.interaction.movil_menu_icon = "close"
            } else {
                this.interaction.menu_movil_action = "#id-menu"
                this.interaction.movil_menu_icon = "menu"
            }
        },
        menu_movil_close() {
            this.interaction.movil_menu_open = false
        }
    }
}
</script>