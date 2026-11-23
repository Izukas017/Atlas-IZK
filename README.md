<div align="center">

<img src="docs/images/logo.png" alt="Atlas" width="88" height="88">

# Atlas

**El explorador de archivos a la velocidad del pensamiento.**

Un explorador de archivos nativo para Windows, acelerado por GPU y que trabaja en local. Hecho con Rust y [GPUI](https://www.gpui.rs/).

[![Web](https://img.shields.io/badge/atlasnative.com-18181B?style=for-the-badge&logo=googlechrome&logoColor=white)](https://atlasnative.com)
[![Microsoft Store](https://img.shields.io/badge/Desc%C3%A1rgalo_en-Microsoft_Store-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](https://apps.microsoft.com/detail/9MX95D1GDMR3)
[![Discord](https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/aeAvQ27bgG)

[![Licencia: AGPL-3.0-or-later](https://img.shields.io/badge/Licencia-AGPL--3.0--or--later-blue.svg)](LICENSE)
[![Hecho con Rust](https://img.shields.io/badge/Hecho_con-Rust-orange.svg)](https://www.rust-lang.org/)
![Estado: alfa](https://img.shields.io/badge/estado-alfa-ff5a1f.svg)

<br>

<img src="docs/images/hero.webp" alt="Vista de cuadrícula de Atlas con iconos por tipo de archivo" width="860">

</div>

<br>

## Por qué Atlas

Atlas dibuja cada píxel en la GPU y mantiene tus archivos en tu equipo. Las carpetas se abren al instante, el desplazamiento sigue fluido incluso en directorios enormes y todo es accesible desde el teclado.

> **Estado:** Atlas está en alfa gratuita para Windows 10/11. Espera algunos fallos y cambios rápidos. Hay una versión para Linux en desarrollo; macOS está en la hoja de ruta.

## Funciones

- **Cinco vistas**: cuadrícula, lista, detalles, columnas Miller y árbol, elegidas por panel.
- **Pestañas y paneles divididos**: divide en cualquier dirección, arrastra y suelta entre paneles y reabre pestañas cerradas.
- **Paleta de comandos**: `Ctrl+Shift+P` ejecuta cualquier comando; `Ctrl+K` salta a cualquier carpeta con búsqueda difusa.
- **Búsqueda instantánea**: búsqueda indexada y difusa que encuentra archivos mientras escribes.
- **Vista previa**: pulsa `Espacio` para previsualizar imágenes, vídeo, audio, documentos, código y archivos comprimidos.
- **Conversión local**: convierte imágenes, vídeo, audio y documentos desde el menú contextual o un selector radial. Los archivos nunca salen de tu PC.
- **Comprimidos como carpetas**: navega por ZIP, RAR, 7z y TAR sin extraerlos.
- **Menú contextual con buscador**: tus propias acciones y el menú nativo de Windows en una sola ventana.
- **Etiquetas, filtros y perfiles**: etiquetas de color, diseños guardados y favoritos por perfil.
- **Carpetas privadas**: carpetas protegidas con contraseña.
- **Limpieza de disco**: descubre qué ocupa espacio y libéralo de forma segura.
- **Nube y red**: Google Drive, OneDrive y otros proveedores mediante rclone, además de SMB, FTP y WebDAV, directamente en la barra lateral.
- **Extensiones**: extensiones oficiales opcionales (temas de iconos, miniaturas, Pandoc, Opus, unidades en la nube, vista previa de documentos).
- **Temas y packs de iconos**: incluidos los temas de iconos de VS Code.

<div align="center">
<img src="docs/images/miller.webp" alt="Columnas Miller con panel de vista previa" width="860">
<br><sub>Columnas Miller con vista previa en directo.</sub>
<br><br>
<img src="docs/images/convert.webp" alt="Selector radial de formato para la conversión local" width="860">
<br><sub>Convierte archivos en local desde un selector radial de formatos.</sub>
<br><br>
<img src="docs/images/grid.webp" alt="Vista de cuadrícula con pestañas" width="860">
<br><sub>Pestañas, ruta de navegación y cuadrícula con iconos reales por tipo de archivo.</sub>
</div>

## Instalación

- **Esta versión (IZK):** descarga `AtlasSetup-0.1.0.exe` desde la [release v0.1](https://github.com/Izukas017/Atlas-IZK/releases/tag/v0.1). Es la edición Full compilada desde el código fuente; requiere permisos de administrador.
- **Microsoft Store:** [Atlas en la Microsoft Store](https://apps.microsoft.com/detail/9MX95D1GDMR3). Gratis; las actualizaciones son automáticas.
- **Web:** [atlasnative.com](https://atlasnative.com) tiene las últimas novedades, el registro de cambios y la lista de espera de Linux.

Atlas es de uso gratuito. Una licencia Premium opcional de pago único amplía los límites (más paneles, perfiles, conexiones en la nube, conversiones y renombrado por lotes); consulta [atlasnative.com](https://atlasnative.com/#pricing).

## Atajos de teclado

Los atajos se pueden cambiar en Ajustes.

| Atajo | Acción |
|---|---|
| `Ctrl+Shift+P` | Paleta de comandos |
| `Ctrl+K` | Ir a carpeta |
| `Ctrl+T` / `Ctrl+W` / `Ctrl+Shift+T` | Nueva / cerrar / reabrir pestaña |
| `Ctrl+Tab`, `Ctrl+1`–`9` | Cambiar de pestaña |
| `Ctrl+Shift+S` / `Ctrl+Alt+S` | Dividir en horizontal / vertical |
| `F6`, `Ctrl+Alt+←→↑↓` | Moverse entre paneles |
| `Alt+←` / `Alt+→` / `Alt+↑` | Atrás / adelante / subir |
| `Ctrl+F`, `Ctrl+Shift+F` | Buscar, buscar en subcarpetas |
| `Espacio`, `Ctrl+I` | Vista previa / inspector |
| `F2` | Renombrar |
| `Ctrl+Z` / `Ctrl+Shift+Z` | Deshacer / rehacer |
| `Ctrl+Alt+C` | Convertir |
| `Ctrl+,` | Ajustes |

## Compilar desde el código fuente

Requisitos: Windows 10/11, las herramientas de compilación de MSVC (Visual Studio Build Tools con el SDK de Windows) y [Rust](https://rustup.rs/). El repositorio fija la versión de la toolchain en [`rust-toolchain.toml`](rust-toolchain.toml), así que `cargo` elige la versión correcta automáticamente.

```powershell
git clone https://github.com/neondeex/atlas-filemanager.git
cd atlas-filemanager

cargo run --release          # ejecutar Atlas
cargo check --workspace      # comprobar tipos de todo
cargo test --workspace       # ejecutar los tests
```

La primera compilación compila GPUI y tarda un rato. Hay alias útiles en [`.cargo/config.toml`](.cargo/config.toml). Para probar los límites opcionales de la edición Free, consulta [Ediciones de compilación](docs/build-editions.md).

## Estructura del proyecto

| Ruta | Qué contiene |
|---|---|
| `crates/atlas-model` | Tipos de datos compartidos y estado de la aplicación |
| `crates/atlas-core` | Sistema de archivos, búsqueda, vista previa, conversión, comprimidos, nube |
| `crates/atlas-ui` | La aplicación GPUI: vistas, ventanas superpuestas, entrada, arrastrar y soltar |
| `crates/atlas-win-space` | Motor de espacio en disco y limpieza para Windows |
| `crates/atlas-search-service` | Servicio de índice de búsqueda en segundo plano |
| `extensions/` | Extensiones oficiales declarativas y sidecar |
| `vendor/` | Forks parcheados de GPUI y gpui-component (Apache-2.0) |
| `docs/` | Guías para colaboradores y autores de extensiones |

Lee [ARCHITECTURE.md](ARCHITECTURE.md) para conocer las reglas de dependencias y [docs/extensions.md](docs/extensions.md) para escribir una extensión.

## Contribuir

Los informes de errores, ideas y pull requests son bienvenidos. Lee primero [CONTRIBUTING.md](CONTRIBUTING.md), abre un [issue](https://github.com/neondeex/atlas-filemanager/issues) para comentar cambios grandes y únete al [Discord](https://discord.gg/aeAvQ27bgG) para hablar con los desarrolladores. Para informar de una vulnerabilidad, consulta [SECURITY.md](SECURITY.md).

## Licencia

Atlas tiene licencia [GNU AGPL v3.0 o posterior](LICENSE). Los componentes de terceros mantienen sus propias licencias; consulta [NOTICE](NOTICE) y [`legal/THIRD-PARTY-NOTICES.txt`](legal/THIRD-PARTY-NOTICES.txt).

El nombre y el logo de Atlas no están cubiertos por la licencia AGPL.
