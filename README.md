# DistantSolar ☀️

Un plugin optimizado desarrollado en Kotlin para servidores de Minecraft (1.19.4+). DistantSolar te permite administrar el `view-distance` y `simulation-distance` de forma individual por cada mundo para mejorar drásticamente el rendimiento de tu servidor y reducir el lag en los chunks.

## Características ✨
* **Gestión por Mundo:** Configura diferentes distancias de renderizado y simulación según el mundo (Ej: menos carga en el Nether, más en el End).
* **Cero Lag:** Optimizado para la API de PaperMC.
* **Comandos Simples:** Incluye comando de recarga en vivo (`/distantsolar reload`) y autocompletado nativo.
* **Organizado:** Todos los archivos de datos se guardan limpiamente dentro de una subcarpeta `/data`.
* **bStats Integrado:** Estadísticas de uso anónimas para monitorear el alcance del plugin.

## Comandos y Permisos 📜

| Comando | Descripción | Permiso |
| :--- | :--- | :--- |
| `/distantsolar help` | Muestra el menú de ayuda. | N/A |
| `/distantsolar reload` | Recarga el archivo de configuración y aplica los cambios inmediatamente. | `distantsolar.admin` |

*(También puedes usar el alias `/dsolar`)*

## Configuración (`data/config.yml`) ⚙️
El archivo de configuración se generará automáticamente en la ruta `plugins/DistantSolar/data/config.yml`.

```yaml
worlds:
  world:
    view-distance: 8
    simulation-distance: 6
  world_nether:
    view-distance: 6
    simulation-distance: 5
  world_the_end:
    view-distance: 10
    simulation-distance: 8
