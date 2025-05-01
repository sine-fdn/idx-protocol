# Impact Data Xchange (IDX) Protocol

The IDX Protocol is a technical specification for achieving interoperability in the impact investments space. It enables the seamless and interoperable exchange of investment opportunity data between different systems.

## Overview

The IDX Protocol aims to serve impact investors and investees by increasing the efficiency of deal sourcing through the exchange of investment opportunity data. The interoperability enabled by the protocol supports:

1. Reducing friction and cost of impact investment decision making for both investors and investees
2. Increasing the number of investments in SDG-related solutions
3. Improving transparency and accountability of impact investments

## Key Components

### Data Model

The IDX Data Model consists of the `Opportunity` data type that contains information relating to a single investment opportunity. It includes properties such as:

- Unique identifier and lifecycle management (`id`, `previousIds`, `status`)
- Basic information about the entity (`companyName`, `email`, `city`, `country`)
- Funding details (`fundingAsk`, `fundingCurrency`)
- Optional information about sustainable practices, previous investors, income sources, and cost structure

### Protocol

The IDX Protocol defines an HTTP-based API for the interoperable exchange of opportunity data between host systems. Key aspects include:

1. **Authentication Flow**: Host systems must implement OAuth2 client credentials authentication
   - Authentication endpoint discovery via OpenID Connect discovery document
   - Bearer token authentication

2. **Actions**:
   - `OpportunityExchange`: Lists the data owner's opportunity data with support for pagination

3. **Host System Requirements**:
   - Must offer an OpenID Provider Configuration Document
   - Must implement the Authentication Flow and OpportunityExchange action
   - Must offer actions under HTTPS only

## Data Transactions

The protocol currently supports the following data transaction:

**Opportunity Data Exchange**: Enables an investee (such as a farmer or cooperative) to make investment opportunity data available to investors or impact funds. It also allows investors to share opportunities with other investors.

## Implementation

Host systems implementing the IDX Protocol must:

1. Offer a discoverable authentication endpoint
2. Implement OAuth2 client credentials authentication
3. Provide opportunities through the defined HTTP API endpoints
4. Support pagination for opportunity data
5. Handle the lifecycle of opportunities (creation, updates, closing)

## Scope Limitations

The following topics and concerns are not within the scope of this specification:

1. KYC or AML-related topics
2. Legal or regulatory aspects of impact investments
3. The definition of impact investment or the impact investments space
4. Data provenance and data security aspects

## Testing and Conformance

The protocol includes a conformance testing framework to assess interoperability between host systems. Test cases are categorized as:

- **Mandatory Tests**: Required for conformance (authentication discovery, successful authentication, opportunity exchange)
- **Recommended Tests**: Additional tests to demonstrate robustness (error handling, pagination, etc.)

## Usage notice

The exchange protocol is made available under the Creative Commons [CC BY-SA](https://creativecommons.org/licenses/by-sa/4.0/) license. This license enables reusers to distribute, remix, adapt, and build upon the material in any medium or format, so long as attribution is given to the creator. The license allows for commercial use. If you remix, adapt, or build upon the material, you must license the modified material under identical terms.