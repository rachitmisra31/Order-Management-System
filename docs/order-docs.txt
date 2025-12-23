# Order Lifecycle Design (V1)

## Objective
Explain the lifecycle of an order in the system and define valid state transitions.

## Order States
- CREATED
- CONFIRMED
- FAILED

## State Definitions

### CREATED
- Order record is created in the system
- Inventory reservation not yet guaranteed

### CONFIRMED
- Inventory successfully reserved
- Order is guaranteed to be fulfilled

### FAILED
- Order cannot be fulfilled
- Terminal state

## Allowed Transitions

| From | To | Allowed |
|------|----|---------|
| CREATED | CONFIRMED | Yes |
| CREATED | FAILED | Yes |
| CONFIRMED | FAILED | No |
| FAILED | Any | No |

## Design Decisions
- Order is modeled as a state machine
- Minimal states introduced initially
- Additional states will be added only when required by business complexity
