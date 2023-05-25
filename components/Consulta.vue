<template>
    <div class="container-consulta">
        <div class="row-consulta">
            <div class="offset">
                <div>
                    <h1>Consulta tu informacíon</h1>
                </div>
                <div class="panel panel-primary">
                    <div class="panel-heading">Criterios de la búsqueda</div>
                    <div class="panel-body">
                        <div class="text-center divBotonesFiltro text-nowrap">
                            <div role="group" class="btn-group">
                                <button class="btn" type="button"
                                    @click="consulta_por_placa">
                                    Por Placa
                                </button>
                                <button class="btn" type="button"
                                    @click="consulta_por_documento">
                                    Por Documento
                                </button>
                            </div>
                        </div>
                        <!-- <form target="mainFrame" method="post" name="mainForm" action="jcrS00Alias" id="form01"> -->
                        <form class="form-horizontal" id="form01">
                            <div class="form-group divCriterioBusqueda">
                                <div class="offset divConsultaCampo" id="consulta_por_placa"
                                    :style="{ display: interaction.placa ? 'inline-block' : 'none' }">
                                    <input type="tel" class="form-control" id="txtRuc" name="search1"
                                        placeholder="Ingrese numero de placa"
                                        pattern="([0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9])"
                                        tabindex="1">
                                        <!-- maxlength="11"  -->
                                </div>
                                <div class="form-control divConsultaCampo" id="consulta_por_documento"
                                    :style="{ display: interaction.documento ? 'inline-block' : 'none' }">
                                    <select name="tipdoc" class="form-control">
                                        <option value="1" selected="">Documento Nacional de Identidad</option>
                                        <option value="4">Carnet de Extranjeria</option>
                                        <option value="7">Pasaporte</option>
                                        <option value="A">Ced. Diplomática de Identidad</option>
                                    </select>
                                    <label>
                                        <input class="form-control" type="text" id="cat1" required="true">
                                    </label>
                                    <p id="total"></p>
                                </div>
                            </div>
                            <div class="form-group">
                                <div class="col-sm-12 text-center">
                                    <nuxt-link to="/consultainfo" class="btn btn-primary">Buscar</nuxt-link>
                                </div>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
        <div class="footer-consulta">
            <p><small>© 2023 CapitalTours Derechos Reservados</small></p>
        </div>
    </div>
</template>
<script>
    export default {
        mounted() {

        },
        data() {
            return {
                interaction: {
                    placa: true,
                    documento: false
                }
            };
        },
        methods: {
            consulta_por_placa() {
                this.interaction.placa = true;
                this.interaction.documento = false;
            },

            consulta_por_documento() {
                this.interaction.placa = false;
                this.interaction.documento = true;
            },
        }
    };
</script>