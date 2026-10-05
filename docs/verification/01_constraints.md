| Constraint ID | Constraint (Simple English) | Reason / Necessity |
|---|---|---|
| C01 | When a train is approaching the crossing, the warning lights must activate before the train reaches the crossing. | Prevents motorists from entering the crossing while the train is still approaching. |
| C02 | If a train is detected on the approach track, the barrier must lower before the train reaches the crossing. | Ensures the crossing is physically closed in time to protect road users. |
| C03 | When the barrier is down, the road signal must display a stop indication. | Prevents vehicles from proceeding into a closed crossing. |
| C04 | If no train is approaching and the crossing is clear, the barrier must remain raised and road traffic must be allowed through. | Restores normal operation and minimizes unnecessary road delays. |
| C05 | If a track sensor fails, the system must enter degraded mode and request manual verification. | A failed sensor can create false positives or missed detection, so manual review is required. |
| C06 | If a barrier actuator fails to lower or raise, the system must raise an alarm and assume a safe-stop state. | A failed barrier is a critical safety risk and must default to the safest condition. |
| C07 | If communication between the control logic and field equipment is lost, the crossing must default to safe operation and display a maintenance alarm. | Lost communication can cause uncoordinated actuation; safe default behavior is essential. |
| C08 | In emergency mode, the control system must prioritize crossing safety over traffic throughput and activate protective actions. | Emergency conditions require maximum protection, even at the cost of vehicle delay. |
| C09 | In emergency override mode, the crossing may only be opened after operator confirmation and controlled clearance procedures. | Prevents unauthorized opening under emergency conditions. |
| C10 | The system must log all faults, sensor states, and state transitions for audit, diagnosis, and maintenance. | Reliable records are necessary for safety assurance and post-incident analysis. |
