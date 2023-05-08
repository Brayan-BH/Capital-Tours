<template>
    <div class="contact_form">

        <div class="formulario">
            <h1 class="form_title">Formulario de contacto</h1>
            <h3 class="form_subtitle">Escríbenos y en breve los pondremos en contacto contigo</h3>
            <form>
                <p>
                    <label for="nombre" class="colocar_nombre">Apellidos y Nombres
                        <span class="obligatorio">*</span>
                    </label>
                    <input class="input_contact" type="text" name="introducir_nombre" id="nombre" required="obligatorio"
                        placeholder="Escribe tus Apellidos y Nombres">
                </p>

                <p>
                    <label for="email" class="colocar_email">Correo Electronico
                        <span class="obligatorio">*</span>
                    </label>
                    <input class="input_contact" type="email" name="introducir_email" id="email" required="obligatorio"
                        placeholder="Escribe tu Email">
                </p>

                <p>
                    <label for="telefone" class="colocar_telefono">Teléfono
                        <span class="obligatorio">*</span>
                    </label>
                    <input class="input_contact" type="tel" name="introducir_telefono" id="telefono"
                        placeholder="Escribe tu teléfono">
                </p>

                <p>
                    <label for="asunto" class="colocar_asunto">Asunto
                        <span class="obligatorio">*</span>
                    </label>
                    <input class="input_contact" type="text" name="introducir_asunto" id="assunto" required="obligatorio"
                        placeholder="Escribe un asunto">
                </p>

                <p>
                    <label for="mensaje" class="colocar_mensaje">Mensaje
                        <span class="obligatorio">*</span>
                    </label>
                    <textarea name="introducir_mensaje" class="input_mensaje" id="mensaje" required="obligatorio"
                        placeholder="Deja aquí tu comentario..."></textarea>
                </p>
                <div class="container_button_contact">
                    <button class="button-2" type="submit" name="enviar_formulario" id="enviar">
                        <p>Enviar</p>
                    </button>
                </div>
                <!-- <p class="aviso">
                    <span class="obligatorio"> * </span>
                    los campos son obligatorios.
                </p> -->
            </form>
        </div>
    </div>

    <!-- creado por javiniguez.com, Julio 2019 -->
</template>