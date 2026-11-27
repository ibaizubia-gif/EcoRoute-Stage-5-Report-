# 2. Methodology & Workflow

## 2.1 System Workflow
1. **Receive Delivery Orders** – the system collects the day's e-commerce orders.
2. **Validate Customer Addresses** – each delivery address is checked before planning.
3. **Check Fleet Availability** – available vehicles and their capacity are reviewed.
4. **Calculate Optimal Routes (AI)** – the AI engine builds routes based on distance, time and capacity.
5. **Estimate CO₂ Emissions** – the emissions of each planned route are calculated.
6. **Dispatch Vehicles** – approved routes are assigned and vehicles leave the depot.
7. **Record Delivery Results** – completed deliveries and route data are stored for analysis.

## 2.2 Decision Logic and Error Handling
| Decision | Yes path | No path |
|---|---|---|
| Addresses valid? | Check Fleet Availability | Request Address Correction, then validate again |
| Enough vehicle capacity? | Calculate Optimal Routes | Reschedule Extra Orders, then check again |
| Emissions within target? | Dispatch Vehicles | Assign Low-Emission Vehicle, then recalculate |
| All deliveries completed? | Record Delivery Results | Reschedule Failed Deliveries, then recalculate |

## 2.3 AI Report Generation
The written documentation was drafted with a structured system prompt (Persona, Context, Task and Constraints blocks, step-by-step reasoning, few-shot examples) that returns `INSUFFICIENT_DATA` for any missing value. The prompt passed four red teaming tests: roleplay override, indirect prompt injection, missing data and prompt leak.

## 2.4 Data Requirements
- Customer orders: order ID, delivery address and time window.
- Fleet data: vehicle type, availability, load capacity and emission factor.
- Route data: distances and expected travel times between delivery points.
- Delivery results: status of each delivery (completed / failed).
