# Technical Architecture

```mermaid
graph TD
    User[Trader] --> Frontend
    Frontend --> SmartContracts
    SmartContracts --> OracleFeeds
    SmartContracts --> AIAgent
    AIAgent --> FundingRates
    OracleFeeds --> ProbabilityIndex
    Token[$P2 Token] --> Governance
