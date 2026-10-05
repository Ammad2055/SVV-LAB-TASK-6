### Variable Definitions
| Variable Name | Data Type | Description |
|---|---|---|
| train_approaching | Boolean | True when a train is detected approaching the crossing. |
| train_detected | Boolean | True when a train is detected on the approach track. |
| warning_lights_on | Boolean | True when the crossing warning lights are active. |
| barrier_down | Boolean | True when the road barrier is fully lowered. |
| road_signal_stop | Boolean | True when the road signal indicates stop. |
| track_clear | Boolean | True when no train is present in the crossing zone. |
| sensor_failure | Boolean | True when a track or approach sensor is not operating correctly. |
| degraded_mode | Boolean | True when the system is operating in a reduced-safety manual-inspection mode. |
| barrier_failure | Boolean | True when the barrier actuator or mechanism has failed. |
| alarm_raised | Boolean | True when a safety alarm is activated. |
| safe_stop_state | Boolean | True when the crossing is held in a safe protective state. |
| communication_loss | Boolean | True when control-to-field communication is interrupted. |
| maintenance_alert | Boolean | True when a maintenance or fault warning is displayed. |
| emergency_mode | Boolean | True when emergency procedures are active. |
| road_signal_go | Boolean | True when the road signal allows vehicles to proceed. |

### Formalized Constraints
| Constraint ID | Description (Simple English) | Formal Logical Expression |
|---|---|---|
| C01 | If a train is approaching, the warning lights must be on. | train_approaching → warning_lights_on |
| C02 | If a train is detected and the crossing is not clear, the barrier must be down. | (train_detected ∧ ¬track_clear) → barrier_down |
| C03 | If the barrier is down, the road signal must show stop. | barrier_down → road_signal_stop |
| C04 | If no train is approaching and the track is clear, the barrier is raised and the road signal allows traffic. | (¬train_approaching ∧ track_clear) → (¬barrier_down ∧ road_signal_go) |
| C05 | If a sensor fails, the system enters degraded mode and raises a maintenance alert. | sensor_failure → (degraded_mode ∧ maintenance_alert) |
| C06 | If the barrier fails, an alarm is raised and the crossing enters safe-stop. | barrier_failure → (alarm_raised ∧ safe_stop_state) |
| C07 | If communication is lost, the crossing defaults to safe operation and a maintenance alert is displayed. | communication_loss → (safe_stop_state ∧ maintenance_alert) |
| C08 | When emergency mode is active, the system prioritizes safety and keeps the crossing protected. | emergency_mode → (warning_lights_on ∧ barrier_down ∧ ¬road_signal_go) |