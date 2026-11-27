# 3. Fleet & Emissions

## 3.1 Fleet Model
| Vehicle | Capacity | Emission factor |
|---|---|---|
| Bicycle | INSUFFICIENT_DATA | INSUFFICIENT_DATA |
| Scooter | INSUFFICIENT_DATA | INSUFFICIENT_DATA |
| Motorcycle | INSUFFICIENT_DATA | INSUFFICIENT_DATA |
| Van | INSUFFICIENT_DATA | INSUFFICIENT_DATA |

Capacity and emission figures have not been collected yet, so they are marked as `INSUFFICIENT_DATA` instead of being estimated.

## 3.2 Vehicle Selection Logic
When a route exceeds the emissions target, the system assigns a lower-emission vehicle (for example, a bicycle or scooter instead of a van) and recalculates the route, as long as the vehicle has enough capacity for the orders.

## 3.3 Limitations and Next Steps
- Collect capacity and emission factors for the four vehicles.
- Define the emissions target used in the "Emissions within target?" decision.
- Select and test the AI routing algorithm with sample delivery data.
- Add a "Notify Customer of Delay" path when no vehicle is available.
