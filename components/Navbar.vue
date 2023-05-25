<template>
    <!-- Navbar -->
    <header class="header-page" itemscope="itemscope">
        <div class="head-container">
            <div class="container__item">
                <div class="item__button_menu" ref="button_movil_menu">
                    <nuxt-link :href="interaction.menu_movil_action" class="item-button-menu__href"
                        @click="menu_movil_click">
                        <div class="item-button-menu__container">
                            <i class="material-icons">{{ interaction.movil_menu_icon }}</i>
                        </div>
                    </nuxt-link>
                </div>
                <nuxt-link class="item__logo" itemprop="url" href="/">
                    <img class="logo__img" src="/img/logo.png" alt="logo">
                </nuxt-link>
                <div class="item__div">
                    <nuxt-link class="div__text" to="/">
                        <span>Capital Tours</span>
                    </nuxt-link>
                </div>
                <nav id="id-menu" class="item__menu" :class="[interaction.movil_menu_open ? 'open' : '']">
                    <ul class="menu_ul">
                        <li class="ul__li" id="linksNav" @click="menu_movil_close">
                            <nuxt-link to="/" class="li__text" :class="{ 'active': selected === 0 }"
                                @click="activeBar(0)">Inicio</nuxt-link>
                        </li>
                        <li class="ul__li" id="linksNav" @click="menu_movil_close">
                            <nuxt-link to="/nosotros" class="li__text" :class="{ 'active': selected === 1 }"
                                @click="activeBar(1)">Nosotros</nuxt-link>
                        </li>
                        <li class="ul__li" id="linksNav" @click="menu_movil_close">
                            <nuxt-link to="/app" class="li__text" :class="{ 'active': selected === 2 }"
                                @click="activeBar(2)">Descargas</nuxt-link>
                        </li>
                        <li class="ul__li" id="linksNav" @click="menu_movil_close">
                            <nuxt-link to="/contactanos" class="li__text" :class="{ 'active': selected === 3 }"
                                @click="activeBar(3)">Contáctanos</nuxt-link>
                        </li>
                        <li class="ul__li" id="linksNav" @click="menu_movil_close">
                            <nuxt-link to="/conductor" class="li__text" :class="{ 'active': selected === 4 }"
                                @click="activeBar(4)">Conductores</nuxt-link>
                        </li>
                        <li class="ul__li" id="linksNav" @click="menu_movil_close">
                            <nuxt-link to="/servicios" class="li__text" :class="{ 'active': selected === 5 }"
                                @click="activeBar(5)">Servicios</nuxt-link>
                        </li>
                        <li class="ul__li" id="linksNav" @click="menu_movil_close">
                            <nuxt-link to="/requisitos" class="li__text" :class="{ 'active': selected === 6 }"
                                @click="activeBar(6)">Requisitos</nuxt-link>
                        </li>
                    </ul>

                </nav>
                <div class="item__action">
                    <div class="action-container">
                        <div class="action__control">
                            <div class="control__container">
                                <div class="container__text cl-session">
                                    <nuxt-link to="/consulta" class="li__text" :class="{ 'active': selected === 7 }"
                                @click="activeBar(7)">Consulta</nuxt-link>
                                </div>
                                <div class="container__icon">
                                    <nuxt-link to="/consulta" class="material-icons">search</nuxt-link>
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
            },
            selected: null
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
            this.interaction.movil_menu_open = false;
            this.interaction.movil_menu_icon = "menu";

        },
        activeBar(index) {
            this.selected = index;
        },
    }
}
</script>