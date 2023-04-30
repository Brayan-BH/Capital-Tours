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
                                <button id="btnPorRuc" class="btn btn-default active btnPor" type="button">Por RUC</button>
                                <button id="btnPorDocumento" class="btn btn-default btnPor" type="button">Por
                                    Documento</button>
                                <button id="btnPorRazonSocial" class="btn btn-default btnPor" type="button">Por
                                    Nomb./Raz.Soc.</button>
                            </div>
                        </div>
                        <!-- <form target="mainFrame" method="post" name="mainForm" action="jcrS00Alias" id="form01"> -->
                        <form class="form-horizontal" role="form" method="post" name="mainForm" action="jcrS00Alias"
                            id="form01">
                            <input type="hidden" name="accion" id="accion" value="">
                            <input type="hidden" name="razSoc" id="razSoc" value="">
                            <input type="hidden" name="nroRuc" id="nroRuc" value="">
                            <input type="hidden" name="nrodoc" id="nrodoc" value="">
                            <input type="hidden" name="token" id="token" value="">
                            <input type="hidden" name="contexto" id="contexto" value="ti-it">
                            <input type="hidden" name="modo" id="modo" value="1"><!-- modo móvil -->
                            <div class="form-group divCriterioBusqueda">
                                <div class="offset divConsultaCampo" id="divRuc">
                                    <input type="tel" class="form-control" id="txtRuc" name="search1"
                                        placeholder="Ingrese RUC"
                                        pattern="([0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9]|[0-9])"
                                        tabindex="1"><!-- maxlength="11"  -->
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