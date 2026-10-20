# Neon Genesis Evangelion (Nintendo 64) — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Ficha del proyecto, capturas y más traducciones al castellano en **[Parches en Castellano](https://parchesencastellano.com/traducciones/nintendo-64/neon-genesis-evangelion)**.

Traducción al **español de España** de *Neon Genesis Evangelion* (Nintendo 64, 1999),
el juego de acción de Bandai que recorre la serie de Gainax en trece misiones y que
solo salió en Japón.

La traducción se reparte como **parche**: no incluye el juego. Necesitas tu propia
copia de la versión japonesa para aplicarlo.

## Estado

Versión **[v1.0](../../releases/tag/v1.0)**: primera versión publicada.

| Parte | Estado |
|---|---|
| Subtítulos de las escenas y fichas de misión | **Completos**: 219 textos traducidos directamente del japonés |
| Texto dentro de imágenes | **321 imágenes rehechas**: títulos de misión, rótulos de escena, pantallas de instrucciones, menús, indicadores de combate, resultados, simulación y créditos |
| Caracteres españoles | **á é í ó ú ü ñ Á É Í Ó Ú Ü Ñ ¡ ¿ « »** |
| Revisión durante una partida | Parcial (ver abajo) |

La traducción se ha hecho desde el japonés con una biblia de términos fija:
**Ángel**, **Unidad 01**, **campo AT**, **Segundo Impacto**, **Tokio-3**, **GeoFront**…
Los subtítulos usan una fuente nueva de ancho variable, con tildes y signos de
apertura, y con el mismo contraste que el original: letra clara con contorno oscuro.

Se han dejado como en el original los logotipos y rótulos de marca, que no hacen
falta para seguir la historia. Lo mismo con el inglés decorativo de las pantallas
de NERV («OBJECT 15th ANGEL», «SIGNAL LOST»…).

### Comprobaciones y limitaciones

Todo se ha probado en emulador (parallel-n64 con el renderizador angrylion).

- **Jugado desde partida nueva:** menús, la misión 1 completa (intro, ficha,
  instrucciones, combate ganado, resultado y guardado), una partida perdida
  («¿Continuar?»), la carga de la partida guardada y el comienzo de la misión 2.
- **Vistas con una ruta de depuración:** todas las escenas de historia de las
  misiones 4 a 13 y los finales. Se entra en cada escena sin jugar las misiones
  anteriores, revisando subtítulos, rótulos y fichas.
- **No se ha jugado una partida completa** de principio a fin, ni se ha probado en
  consola real ni en flashcart.
- No se han podido ver en el juego el modo **Simulación** (también aparece
  bloqueado en el original al empezar) ni el minijuego de **contraseña** de la
  misión 4. Sus imágenes están traducidas, pero solo se han comprobado fuera del
  juego.
- Cinco nombres de los créditos finales siguen en japonés porque no se ha podido
  confirmar su lectura.
- En el montaje rápido del final, alguna imagen puede verse un instante con los
  colores cambiados. El juego carga ahí la paleta con un fotograma de retraso, y
  el original lo hace igual de a menudo.
- La traducción y las revisiones se han hecho con ayuda de modelos de IA. No ha
  habido una revisión humana independiente.

Si encuentras un error, abre una incidencia indicando la misión y, si puedes,
una captura.

## Cómo aplicar el parche

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia del juego en versión **japonesa**, en formato **.z64**
   (big-endian). Si tienes un `.n64` o un `.v64`, conviértelo antes a `.z64`
   (por ejemplo con Tool64).
3. **Comprueba que tu copia es la correcta** antes de nada:

   | | |
   |---|---|
   | Archivo | `Neon Genesis Evangelion (Japan).z64` |
   | Tamaño | 33.554.432 bytes (32 MB) |
   | MD5 | `5e1940ca1236a76e8f2d15de0414ae55` |

   ```bash
   md5sum "Neon Genesis Evangelion (Japan).z64"     # Linux
   md5 "Neon Genesis Evangelion (Japan).z64"        # macOS
   CertUtil -hashfile "Neon Genesis Evangelion (Japan).z64" MD5   # Windows
   ```

   Si no coincide, el parche fallará o dará un resultado corrupto.
4. Aplica el parche con una de estas herramientas:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**: `xdelta3 -d -s "Neon Genesis Evangelion (Japan).z64" Neon.Genesis.Evangelion.N64.ES.v1.0.xdelta "Neon Genesis Evangelion (ES).z64"`
5. Comprueba que la ROM resultante tiene MD5 **`e1c1937c7582bad1767d82243e0a73b0`**.
6. Cárgala en tu emulador o flashcard.

### Guardado (importante)

El juego usa **EEPROM de 16 Kbit**. Los emuladores reconocen el juego original
por su huella, pero no la ROM traducida. Por eso el parche le pone a la ROM la
**cabecera avanzada de homebrew** (identificador «ED», guardado EEPROM 16K), que
mupen64plus, RetroArch (Mupen64Plus-Next y ParaLLEl), ares, simple64 y EverDrive
leen solos. La suma de comprobación de la cabecera es la del original, así que
arranca en consola y Project64 la sigue reconociendo.

Si el juego **se queda en negro al arrancar**, tu emulador está usando EEPROM 4K:
cambia a mano el tipo de guardado a **EEPROM 16K (16 Kbit)**.

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin
relación alguna con Bandai, Gainax, khara ni los titulares de *Neon Genesis
Evangelion*. Aquí no se distribuye el juego ni ninguna parte de él: solo un
parche que modifica una copia que ya tengas.

Si eres el titular de los derechos y quieres que retire esto, abre una incidencia
y lo hago.
