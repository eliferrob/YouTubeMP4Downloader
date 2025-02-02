# YouTubeMP4Downloader
Script creado en Python que emplea la herramienta **yt-dlp** para descargar vídeos de YouTube. Ofrece la opción de elegir la calidad del vídeo (1080p o 720p), e incrusta, a su vez, la miniatura.
La descarga se hará con la mejor calidad de imagen y sonido, y el fichero resultante se guardará en el escritorio del usuario en formato MP4.

## Instalación

### Clonar repositorio

```bash
git clone https://github.com/eliferrob/YouTubeMP4Downloader.git
```

### Instalar dependencias

Moverse a la carpeta contenedora:

```bash
cd YouTubeMP4Downloader
```

El script requiere los siguientes módulos para funcionar:
 - [ffmpeg](https://github.com/BtbN/FFmpeg-Builds/releases)
 - [yt-dlp](https://github.com/yt-dlp/yt-dlp/releases)

Puedes descargarlos manualmente o ejecutar este comando:

```bash
pip install -r requirements.txt
```

## Corrección de errores

Cada video ofrece múltiples formatos disponibles para su descarga, por lo que no es posible establecer un formato predeterminado universal. El script automatiza esta selección, eligiendo la primera opción que cumpla con los requisitos de calidad de video y audio que el usuario introduce por teclado.

En algunos casos, los formatos seleccionados pueden no ser compatibles con MP4, por lo que se descargarán en WEBM. Para solucionar esto:

1. Ejecuta el comando `yt-dlp -F <URL>` para listar los formatos disponibles del video.
2. Identifica el rango de formatos que te interesan.
3. Copia el ID del formato deseado.
4. Sustituye el valor de la variable _quantity_ en las líneas 51 o 53 del script por el ID elegido.

De esta manera, el vídeo se descargará con con formato correcto. 😊
