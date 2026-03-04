# ☀️ DistantSolar

Un plugin avanzado y altamente optimizado, desarrollado en **Kotlin**, diseñado para servidores de Minecraft (1.19.4+). DistantSolar te permite administrar el `view-distance` y `simulation-distance` de forma individual por cada mundo para mejorar drásticamente el rendimiento de tu servidor y erradicar el lag.

## ✨ Características Principales
* **Gestión Independiente:** Configura distancias de renderizado y simulación personalizadas para cada mundo (Overworld, Nether, The End, etc.).
* **Cero Lag:** Optimizado nativamente para la API de PaperMC.
* **Colores Hex y RGB:** Soporte total para códigos de color modernos (`&#FFAA00` o `#FFAA00`) en todos los mensajes.
* **Personalización Total:** Edita cada mensaje, prefijo y permiso desde la configuración. (Puedes desactivar el prefijo simplemente poniendo `prefix: false`).
* **Sistema de Permisos Dinámico:** Asigna permisos personalizados a cada comando o usa `default` para que cualquier jugador pueda usarlo sin necesidad de OP.
* **API para Desarrolladores:** Permite a otros plugins obtener y modificar las distancias de los mundos en tiempo real.
* **Métricas Integradas:** Soporte oficial de [bStats](https://bstats.org/plugin/bukkit/DistantSolar/29907) para monitorear el alcance del plugin.

## 📜 Comandos y Permisos

| Comando | Descripción | Permiso por Defecto |
| :--- | :--- | :--- |
| `/dsolar help` | Muestra el menú de ayuda interactivo. | `default` (Todos) |
| `/dsolar view <mundo>` | Muestra el View y Simulation distance actual de un mundo. | `distantsolar.admin` |
| `/dsolar reload` | Recarga la configuración y aplica los cambios al instante. | `distantsolar.admin` |

*(Nota: Todos los permisos son 100% editables en el `config.yml`)*

## ⚙️ Configuración (`config.yml`)
Todos los archivos se generan limpiamente dentro de la carpeta `plugins/DistantSolar/data/`. Si deseas que un mundo use la distancia por defecto del servidor (server.properties), simplemente establece su valor en `-1`.

```yaml
#       ___ _     _              _   __       _
#     /   (_)___| |_ __ _ _ __ | |_/ _\ ___ | | __ _ _ __
#    / /\ / / __| __/ _` | '_ \| __\ \ / _ \| |/ _` | '__|
#   / /_//| \__ \ || (_| | | | | |__\ \ (_) | | (_| | |
#  /___,' |_|___/\__\__,_|_| |_|\__\__/\___/|_|\__,_|_|
#                 Powered by xPlugins.es

# Configura la distancia de visión y simulacion por cada mundo.
# Si pones -1, el plugin ignorará ese valor.
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

# Permisos de los comandos. Si pones "default", cualquier jugador puede usarlo sin op.
permissions:
  help: "default"
  reload: "distantsolar.admin"
  view: "distantsolar.admin"

# Mensajes del plugin. Soporta código de colores & y Hex (Ej: &#FFAA00 o #FFAA00)
# Si no quieres usar prefijo, simplemente pon: prefix: false
messages:
  prefix: "&#FFAA00[&#FFFF55DistantSolar&#FFAA00] "
  no-permission: "&cNo tienes permisos para realizar esta acción."
  reload-success: "&a¡Configuración recargada exitosamente!"
  unknown-command: "&cComando desconocido. Usa &e/dsolar help"
  view-usage: "&cUso correcto: &e/dsolar view <mundo>"
  world-not-found: "&cEl mundo &e%world% &cno existe o no está cargado."
  view-info: "&fEl mundo &#FFFF55%world% &ftiene View: &#FFAA00%view% &fy Sim: &#FFAA00%sim%"
  help:
    - "&8&m----------------------------------------"
    - ""
    - "            %prefix% &7v1.0.0"
    - " &e/dsolar reload &8- &fRecarga la configuración."
    - " &e/dsolar view <mundo> &8- &fMira la distancia de un mundo."
    - " &e/dsolar help &8- &fMuestra este menú."
    - ""
    - "&8&m----------------------------------------"

version: 1.0.0
# ¿Quieres ver la estadísticas del plugin?
# Ingresa a bStats (Debe estar activado en el Servidor para que funcione.
# Link: https://bstats.org/plugin/bukkit/DistantSolar/29907
```

## 👨‍💻 API para Desarrolladores (Developers)
DistantSolar expone una API sencilla para que otros plugins puedan interactuar con las distancias de los mundos.

- Ejemplo de uso (Java/Kotlin):

* Kotlin
```import es.xplugins.distantsolar.api.DistantSolarAPI

// Obtener la distancia de visión de un mundo
int view = DistantSolarAPI.getViewDistance("world_nether");

// Cambiar la distancia de simulación en tiempo real
boolean success = DistantSolarAPI.setSimulationDistance("world_the_end", 8);
```
##💡 Créditos
Desarrollado con pasión por xPlugins
