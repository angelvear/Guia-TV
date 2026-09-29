Guía TV 📺

Un visor web moderno, ligero y responsive de guías de programación de televisión (EPG en formato XMLTV). Funciona íntegramente en el navegador (Vanilla JavaScript sin frameworks pesados ni dependencias de backend) y se integra de forma nativa con los catálogos públicos de iptv-org.

✨ Características

Sin dependencias complejas: Todo el proyecto está contenido en un único archivo HTML con Vanilla JS y Tailwind CSS (vía CDN).

Soporte XMLTV completo: Parsea feeds EPG en formato XML estándar y comprimidos con GZIP (.xml.gz) mediante la API nativa DecompressionStream.

Detección automática de fuentes GitHub: Convierte automáticamente URLs de visualización estándar de GitHub (github.com/.../blob/...) a sus enlaces crudos (raw.githubusercontent.com).

En emisión ahora (Now Playing): Tarjeta destacada con barra de progreso en tiempo real y minutos restantes del programa actual.

Navegación temporal: Selector rápido de días (-1 ayer, 0 hoy, +1 mañana y hasta 5 días vista).

Filtros avanzados y búsqueda:

Búsqueda en vivo por nombre de canal.

Filtro por país (con banderas e internacionalización con Intl.DisplayNames).

Filtro por idioma.

Filtro para mostrar únicamente canales favoritos o canales con guía disponible.

Canales favoritos: Guarda tus canales preferidos en el almacenamiento local (localStorage).

Presets integrados: Acceso rápido a guías de España (TDT y operadores) y proveedores internacionales (Sling TV, JioTV, ZEE5, etc.).

Modo Demo offline: Incluye programación y canales de prueba simulados para explorar la interfaz sin conexión o sin cargar un XMLTV.

Tema Claro / Oscuro: Detección automática de preferencia del sistema operativo (prefers-color-scheme) y conmutador manual persistente.

Diseño responsive: Adaptado tanto a escritorio como a pantallas móviles (soporta áreas seguras para dispositivos notch / iOS).

🚀 Puesta en marcha rápida

No requiere ningún proceso de compilación (build) ni entorno Node.js.

Opción 1: Abrir localmente

Clona el repositorio o descarga el archivo:

git clone https://github.com/tu-usuario/guia-tv.git
cd guia-tv


Abre guia-tv.html (o index.html) en cualquier navegador moderno.

Opción 2: Servidor local ligero (recomendado para evitar restricciones CORS locales)

# Con Python 3
python -m http.server 8000

# Con Node.js (npx)
npx serve .


Abre en tu navegador: http://localhost:8000/guia-tv.html.

⚙️ Configuración y fuentes EPG

Por defecto, la aplicación intenta cargar la guía de canales y TDT de España. Puedes modificarla en cualquier momento desde el botón Ajustes en la esquina superior derecha:

Presets: Elige una de las guías preconfiguradas en el desplegable.

URL personalizada: Pega el enlace directo a tu propio archivo XMLTV:

Puede ser un archivo .xml plano o comprimido .xml.gz.

Si usas repositorios generados por iptv-org/epg, puedes pegar la URL directa en formato RAW.

Haz clic en Guardar y cargar.

Nota sobre CORS: La URL del feed XML/GZ debe servirse desde un servidor que permita peticiones de origen cruzado (Access-Control-Allow-Origin: *). Los archivos servidos desde raw.githubusercontent.com o github.io son compatibles por defecto.

🛠️ Tecnologías utilizadas

HTML5 & CSS3 (Variables CSS personalizadas para temas).

Tailwind CSS (CDN) para maquetación rápida y utilidades de interfaz.

Tipografías de Google Fonts: Bricolage Grotesque e Instrument Sans.

Vanilla JavaScript (ES6+):

Web Streams API (DecompressionStream) para descompresión de .gz.

DOMParser para procesar XMLTV.

Intl.DisplayNames e Intl.DateTimeFormat para fechas, regiones e idiomas localizados.

localStorage para persistencia de ajustes, favoritos y tema.

📄 Licencia

Este proyecto se distribuye bajo la licencia MIT. Siéntete libre de modificarlo, adaptarlo e integrarlo en tus proyectos.
