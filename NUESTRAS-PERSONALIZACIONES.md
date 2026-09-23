# Personalizaciones locales de esta copia (NO vienen del upstream)

Esta rama parte del tag upstream `2026.6.3` y añade **13 ficheros** personalizados
en producción (servidor de Àxel). El objetivo es que un update no las borre:

| Fichero | Motivo |
|---|---|
| `device.py` | parche local (núcleo de la integración) |
| `helpers/device_config.py` | parche local (núcleo de la integración) |
| `devices/koiduo_water_heater.yaml` | modos reales del termo (`eco`, `manmenu`, `highwarm`) + nombres en castellano + iconos + rango 30-75/paso 1 |
| `devices/chanfok_fan_light.yaml` | ventilador con luz (lámpara/ventilador habitación matrimonio) |
| `devices/ovlaim_809_ceiling_fanlight.yaml` | ventilador de techo con luz |
| `devices/yamazen_fan.yaml` | ventilador |
| `devices/djive_arc_portable_fan.yaml` | ventilador portátil |
| `devices/duux_whisper_flex_ultimate_fan.yaml` | ventilador |
| `devices/rgbcw_lightbulb_xld_cl002.yaml` | bombilla RGB |
| `devices/kktkolbe_easyhcm_rangehood.yaml` | campana extractora |
| `devices/alen_35i_airpurifier.yaml` | purificador de aire |
| `devices/mypin_6l_videopetfeeder.yaml` | comedero de mascotas |
| `devices/omni_x_duplex_waterheater.yaml` | termo |

**Regla:** antes de actualizar la integración, comprobar que estas
personalizaciones siguen presentes (comparar con esta lista).
