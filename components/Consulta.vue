<template>
    <div class="container-consulta">
        <!-- <div class="header" id="divHeader">
            <div class="offset">
                <img src="/img/logo.png" class="imgLogo">
            </div>
        </div> -->
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
                                <button id="btnPorRuc" class="btn btn-default  btnPor" type="button"
                                    @click="consulta_por_placa">
                                    Por Placa
                                </button>
                                <button id="btnPorDocumento" class="btn btn-default btnPor" type="button"
                                    @click="consulta_por_documento">
                                    Por Documento
                                </button>
                            </div>
                        </div>
                        <!-- <form target="mainFrame" method="post" name="mainForm" action="jcrS00Alias" id="form01"> -->
                        <form class="form-horizontal" role="form" method="post" name="mainForm" action="jcrS00Alias"
                            id="form01">
                            <div class="form-group divCriterioBusqueda">
                                <div class="offset divConsultaCampo" id="consulta_por_placa">
                                    <input type="tel" class="form-control" id="txtRuc" name="search1"
                                        placeholder="Ingrese RUC"
                                        pattern="([0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9])"
                                        tabindex="1"><!-- maxlength="11"  -->
                                </div>
                                <div class="form-control divConsultaCampo" id="consulta_por_documento">
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
                                    <button type="button" class="btn btn-primary" id="btnAceptar"
                                        tabindex="3">Buscar</button>
                                    <button type="button" class="btn btn-danger" id="btnVolverWorkspace"
                                        style="display: none;">Volver</button>
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
            // Llamar a la función consulta_por_placa al cargar la página
            window.onload = this.consulta_por_placa();
        },
        methods: {
            consulta_por_placa() {
                const consulta_placa = document.getElementById('consulta_por_placa');
                const consulta_documento = document.getElementById('consulta_por_documento');

                consulta_placa.style.display = "inline-block";
                consulta_documento.style.display = "none";
            },

            consulta_por_documento() {
                const consulta_placa = document.getElementById('consulta_por_placa');
                const consulta_documento = document.getElementById('consulta_por_documento');

                consulta_placa.style.display = "none";
                consulta_documento.style.display = "inline-block";
            },



            // Agregar evento onclick al botón correspondiente
            // const btn_consulta_documento = document.getElementById('btn_consulta_documento');


        }
};
</script>