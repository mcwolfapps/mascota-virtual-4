# 🐛🐜 Mascota metálica – asistente

Mascota de piezas metálicas que se mueve sola por la pantalla y te ayuda. Sin dependencias ni build para la versión web.

## Uso (toca la cabeza de la mascota)
- 📝 **Notas** · 🔍 **Buscar** (en tus notas o en la web) · 📅 **Evento** (la mascota pregunta y abre Google Calendar con el evento listo, o descarga .ics)
- 🐾 **Mascotas** (estilo dark: metal obsidiana con halo y articulaciones de neón): 24 en total, agrupadas por insecto y con varios tipos de cada uno.
  - Gratis: Ciempiés y Hormiga.
  - Pro (S/ 1 a S/ 3): variantes de ciempiés, hormigas, mantis, escarabajos, arañas (tarántula, viuda negra, saltadora y una de patas largas), abejas y avispas, mariquitas, libélulas y escorpiones.
- **Ciempiés vs milpiés:** el ciempiés tiene pocas placas planas, una pata por lado y dos patas traseras largas. El milpiés es mucho más largo (30 anillos, crece 2 por nota), con dos pares de patas cortas por segmento y una ola de movimiento.
- **Patas robóticas** (todas las mascotas): eslabones metálicos, pistón, articulaciones de neón y pie. El ciempiés y el milpiés hacen cada 12 s movimientos imposibles para un cuerpo real: 2.5 s de patas-hélice (giran 360°) y 2.5 s de patas-pistón (se alargan y encogen).
- **Arañas:** marcha con pies apoyados (cada pata se planta en el suelo y las ocho siguen un reloj común: dos grupos de cuatro que alternan, sin patinar, con las rodillas siempre hacia afuera). La **Araña patas largas** es de acero con detalles rojos: abdomen acorazado con núcleo rojo pulsante, tibias con banda roja y ojos rojos.
- 🌐 **Web** (necesita internet; al abrir, la mascota lo verifica y lo dice):
  - La primera vez pregunta tu nombre y cómo prefieres que te llame: **Por mi nombre**, **Amigo** (jergas peruanas y bromas) o **Boss** (te trata de jefe/señor si eres hombre, o de jefa/Ma'am/madame si eres mujer). Después se cambia en ⚙️ Ajustes → Perfil.
  - **Hoy:** clima (Open-Meteo) con coordenadas *exactas* o *referenciales* según la precisión del GPS, o por ciudad; feriados (Nager.Date); "un día como hoy" (Wikipedia).
  - **Preguntar:** busca en internet con un buscador de plan gratuito (Tavily, Serper, Exa o Jina). Pega tu clave en ⚙️ Ajustes → Búsqueda de información, o usa el servidor intermedio de `servidor-intermedio/worker.js` (Cloudflare Workers gratis) para no exponer la clave y evitar bloqueos CORS.
  - **Diccionario** (Wiktionary + dictionaryapi.dev, y si no está lo busca en otros idiomas), **Traducir** (MyMemory, hasta 450 caracteres), **Libros** (primero los gratis: Project Gutenberg, Google Libros y Open Library), **Ciencia** (OpenAlex), **Monedas** (Frankfurter), **Espacio** (imagen del día de la NASA con traducción, buscador de la biblioteca de la NASA y asteroides cercanos) y **Estado** (prueba cada servicio y muestra ✅/❌).
  - Solo la NASA usa clave opcional (⚙️ Ajustes); sin ella usa `DEMO_KEY` (unas 30 consultas por hora).
  - La ubicación por GPS solo funciona con HTTPS (por ejemplo GitHub Pages) y con su permiso.
- **Patas con piso** en todas las mascotas que caminan: cada pie se apoya en el suelo y las patas siguen un reloj común (trípode en 6 patas, alternadas en 8, ola en ciempiés y milpiés). Abeja y libélula vuelan, así que llevan las patas recogidas.
- ✨ **Crear mi mascota** (en 🐾 Mascotas): la mascota te hace las preguntas paso a paso (nombre, especie, forma o rasgos, acabado, color del cuerpo y color de las luces) y cambia en vivo mientras eliges. Se guarda en este navegador.
- 💭 **Pensamientos reales:** la mascota piensa en globos de nubecita con cosas de internet (noticias de BBC Mundo, tecnología de Hacker News, espacio de Spaceflight News, un dato del día) y de tu propia información (tus eventos próximos, notas, clima y feriados), sin repetir hasta agotar la lista. Se puede apagar en ⚙️ Ajustes.
- 📅 **Eventos con videollamada:** elige Google Meet, Zoom u otro enlace. Con un botón abres Meet (`meet.google.com/new`) o Zoom, copias el enlace y lo pegas; el evento lo lleva en la ubicación y la descripción. También acepta invitados (correos), copia la invitación y la comparte por WhatsApp. La creación automática de la sala necesita OAuth con Google o Zoom (siguiente etapa).
- ⏱️ **Tiempo:** cronómetro con vueltas y temporizador con alarma (sonido, aviso y mensaje de la mascota).
- ⚙️ **Ajustes:** perfil, buscador, clave NASA, pensamientos y el 💎 modo Pro de prueba (mascotas Pro y eventos avanzados; no cobra nada).: el botón "Pro" de las mascotas o del menú Pro **activa el modo prueba**; desbloquea todo y las etiquetas PRO muestran qué es de pago.
  - Estadísticas de enfoque: cronómetro y gráfico de 7 días (se guarda en el navegador).
  - Eventos avanzados: repetición (diaria/semanal/mensual) y recordatorio.
- Toca fuera o pulsa Esc para cerrar. Los pagos **aún no existen**: el modo prueba es solo para revisar.

## Versión web / PWA
Abre `index.html` o sirve la carpeta (`python3 -m http.server 8000`). En GitHub Pages: Settings → Pages → `main`.
Una página web no puede ser transparente sobre otras apps: verás el fondo de la página.

## Modo escritorio (solo la mascota sobre tus otras apps)
```bash
npm install
npm start
```
Ventana transparente, siempre encima; los clics pasan a tus apps salvo sobre la mascota y su menú. Salir: `Ctrl/Cmd + Shift + Q`.
Probado el diseño para Windows y macOS; en Linux la transparencia y el paso de clics dependen del entorno.

## Siguientes pasos
- Pagos reales (requiere servidor y un proveedor como Stripe) y desbloqueo por cuenta.
- Google Calendar real con OAuth.
- App nativa de Android si quieres la mascota flotando sobre otras apps en el celular.
