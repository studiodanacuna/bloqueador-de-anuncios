
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bloqueador de Anuncios en zonaaps.com</title>
</head>
<body>
    <h1>Prueba del Bloqueador de Anuncios en zonaaps.com</h1>
    <p>Este es un ejemplo de cómo bloquear anuncios en la página especificada.</p>

    <iframe src="https://zonaaps.com/" width="100%" height="800px" id="webpage"></iframe>

    <script>
    function bloquearAnuncios() {
        const iframe = document.getElementById('webpage');
        iframe.onload = function() {
            const iframeDocument = iframe.contentDocument || iframe.contentWindow.document;
            const selectoresDeAnuncios = [
                ".ads",
                ".advertisement",
                "iframe",
                "[id^='ad-']"
            ];

            selectoresDeAnuncios.forEach(selector => {
                const anuncios = iframeDocument.querySelectorAll(selector);
                anuncios.forEach(anuncio => {
                    console.log('Elemento eliminado: ', anuncio);
                    anuncio.remove();  // Eliminar el anuncio
                });
            });

            console.log("Anuncios bloqueados en zonaaps.com.");
        };
    }

    window.onload = bloquearAnuncios;
    </script>
</body>
</html>
