# VehicleTrader

## Overview
This DAML model shows a workflow for the resale of motor vehicles, to be used for an exclusive trading platform. Buyers are rigorously prequalified for the opportunity to buy at heavy discounts, with the expectation of immediate cash settlement only. Vehicles are purchased sight unseen.

### Parties
  - Dealership: Initial seller of the vehicles.
  - Qualified Buyers: Those who have met the financial prequalifications to use the platform.
  - Titling Agency (DMV): The state government agency that issues vehicle titles.

## Workflow Process
  1. Vehicle owner creates a new listing to solicit purchase offers from the pool of qualified buyers.
  2. Buyers submit purchase offers (and may revoke them prior to the owner taking action).
  3. Owner either _declines_ or _accepts_ each offer. Only one offer can be accepted. Once accepted, the listing is placed in 'Pending Sale' state and the owner issues an invoice to the buyer.
  4. If the buyer fails to pay the invoice, the owner may cancel and place the listing back in 'Accepting Offers' state.
  5. Once the buyer pays the invoice, the listing is removed, a Bill of Sale is generated, and a request for transfer of the vehicle's title is submitted to the DMV.
  6. The DMV will analyze the request for fraud. If found, they will flag the request for further investigation. If not found, they will issue a new title to the buyer and update the vehicle's title history records.
  7. The DMV will invoice the buyer for payment of state sales tax (6% of the purchase price).

## Note
  - By default, vehicle owners see only those titles that are active at the time of ownership, plus sale to the next buyer. _However, by state law, **any** individual can request the complete title history of any vehicle (for a fee)._


## Building
To compile the project:
```
daml build
```

## Testing
To test all DAML scripts:
```
daml test --color
```

## Running
To load the project into the sandbox and start navigator:
```
daml start
```

