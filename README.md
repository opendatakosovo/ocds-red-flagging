# ocds-red-flagging
Raising contracting data red flags from a list of OCDS documents and user defined red flag rules.

## Forumalting Rules

### Supported OCDS variables

Variables we can use to formulate rules:

- planning.budget.amount
- contract.value
- contract.implementation.transactions

### Supported operands

| Operand | Description      |
|----|-----------------------|
| == | Equality              |
| != | Inequality            |
| >  | Greater than          |
| >= | Greater than or equal |
| <  | Lesser than           |
| <= | Lesser than or equal  |

### Supported operations

| Operations | Description  |
|---|-----------------------|
| + | Addition              |
| - | Subtraction           |
| * | Multiplication        |
| / | Division              |
| % | Modulo                |

### Supported math functions

| Function | Description |
|-----|------------------|
| abs | Absolute         |


### Sample rules

The contract value is greater than the budget amount:
`contract.value > planning.budget.amount`

The contract value is greater than the budget amount by more than an additional 10%:
`contract.value > (planning.budget.amount + 0.10 * planning.budget.amount)`

The absolute difference between the contract value and the budget amount is less than one hundred:
`abs(planning.budget.amount - contract.value) < 100`

The contract value is zero:
`contract.value == 0`
