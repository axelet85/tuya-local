# Personalizaciones locales — tuya_local 2026.6.3

Esta rama contiene la versión 2026.6.3 de `make-all/tuya-local` con 9
ficheros modificados localmente para nuestro hardware.

## Ficheros modificados

### Núcleo de la integración

| Fichero | Cambio | Motivo |
|---------|--------|--------|
| `device.py` | `socketRetryLimit(1)` en vez de `0` | Evita reconexiones agresivas al dispositivo Tuya. Con `0` el socket se cierra inmediatamente en cualquier error de red; con `1` reintenta una vez, lo que estabiliza la conexión en WiFi inestable. |
| `helpers/device_config.py` | Lógica `_active_condition` para `icon_rule` | Permite que el icono de la entidad cambie según el modo de operación actual (ej: flash para calentamiento, leaf para eco). La versión upstream no soporta esto. |

### Configuraciones de aparatos (11 ficheros)

| Fichero | Aparato | Cambio principal |
|---------|---------|------------------|
| `devices/chanfok_fan_light.yaml` | Ventilador + luz Chanfok | IDs de DPs y estructura adaptados a nuestra unidad física |
| `devices/ovlaim_809_ceiling_fanlight.yaml` | Ventilador de techo Ovlaim 809 | Configuración extendida con modos adicionales |
| `devices/duux_whisper_flex_ultimate_fan.yaml` | Ventilador Duux Whisper Flex Ultimate | IDs de DPs correctos para nuestro modelo |
| `devices/rgbcw_lightbulb_xld_cl002.yaml` | Bombilla RGBW XLD CL002 | Configuración con IDs reales del dispositivo |
| `devices/alen_35i_airpurifier.yaml` | Purificador Alen 35i | Modos de velocidad reales (no los genéricos de upstream) |
| `devices/mypin_6l_videopetfeeder.yaml` | Comedero MyPin 6L | IDs de DPs correctos (237 en vez de 247) |
| `devices/koiduo_water_heater.yaml` | Termo Koi Duo HTW-TD-080 | **Modos en castellano + iconos MDI + rango de temperatura 30-75°C (step 1)**. Upstream solo tenía 2 modos con dps_val incorrecto (`maneco` en vez de `eco`). |
| `devices/yamazen_fan.yaml` | Ventilador Yamazen | Fichero del upstream 2026.6.3 (no modificado localmente) |
| `devices/djive_arc_portable_fan.yaml` | Ventilador DJiVe Arc | Fichero del upstream 2026.6.3 (no modificado localmente) |
| `devices/kktkolbe_easyhcm_rangehood.yaml` | Campana KKT&Kolbe | Fichero del upstream 2026.6.3 (no modificado localmente) |
| `devices/omni_x_duplex_waterheater.yaml` | Termo Omni X Duplex | Fichero del upstream 2026.6.3 (no modificado localmente) |

**Nota**: Los 4 últimos ficheros (yamazen, djive, kktkolbe, omni) están en el upstream
2026.6.3 pero fueron eliminados de producción en algún momento. Se incluyen aquí para
mantener la rama como un superconjunto completo de producción.

## Cómo actualizar

Cuando salga una nueva versión de `make-all/tuya-local`:

1. Haz `git merge 2026.x.x` (la nueva tag upstream)
2. Resuelve conflictos en los 9 ficheros modificados
3. Verifica que los 4 modos del termo siguen funcionando
4. Publica un nuevo tag `2026.x.x-esN`

## build

Preparado con asistencia de IA; el firmante lo entiende y puede probarlo.
