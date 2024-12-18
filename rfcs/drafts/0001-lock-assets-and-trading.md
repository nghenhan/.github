# RFC: [Descriptive Title]

**Authors:** Minh Tran
**Project:** Trading Platform and Funds Management
**Status:** WIP
**Created:** [18/12/2024]
**RFC PR:** [Link to the Pull Request discussing this RFC, once created]

## Summary

Implement how we calculate PnL and prevent user action touch to accounts have locked position include locked for assets and locked for trading

## Motivation

- **What problem does this proposal solve?**
  To help user can trade on locked symbol while locked position is opening

- **Who is affected by this proposal, and how?**
  - **End-users:** Can define action type to let system calculate PnL base on action
  - **Investor:** Can earn more profit from trade and their locked for asset position still safe


## Proposal

### Technical Details
- Add type into API `locked-position`

- Update account trade set worker flow to create locked position trade set if user lock for asset only

- Update script to retrieve trade set base on locked for asset only

### Some scenario examples

#### Locked scenario

1. Open then lock for asset

<div align="center">

```mermaid
flowchart TD
    A[Start] --> B[Open 10 BTC position]
    B --> C[Lock for asset]
    C --> D[Create 10 BTC <br>Locked Position Trade Set]
    D --> E[End]

    style B fill:#f9f,stroke:#333,stroke-width:2px
    style C fill:#bbf,stroke:#333,stroke-width:2px
    style D fill:#bfb,stroke:#333,stroke-width:2px
```

</div>

2. Open then lock for trading

<div align="center">

```mermaid
flowchart TD
    A[Start] --> B[Open 10 BTC position]
    B --> C[Lock for trading]
    C --> D[End]

    style B fill:#f9f,stroke:#333,stroke-width:2px
    style C fill:#bbf,stroke:#333,stroke-width:2px
    style D fill:#bfb,stroke:#333,stroke-width:2px
```

</div>

3. Open then change lock type from trade to asset

<div align="center">

```mermaid
flowchart TD
    A[Start] --> B[Open 10 BTC Position]
    B --> C[Lock for Trading]
    C --> D[Lock for Asset]
    D --> E["Update Lock Type:<br>TRADE → ASSET"]
    E --> F["Create 10 BTC<br>Locked Position Trade Set"]
    F --> G[End]

    style B fill:#f9f,stroke:#333,stroke-width:2px
    style C fill:#bbf,stroke:#333,stroke-width:2px
    style D fill:#bbf,stroke:#333,stroke-width:2px
    style E fill:#bfb,stroke:#333,stroke-width:2px
    style F fill:#f96,stroke:#333,stroke-width:2px
```

</div>

4. Open then change lock type from asset to trade

<div align="center">

```mermaid
flowchart TD
    A[Start] --> B[Open 10 BTC Position]
    B --> C[Lock for Asset]
    C --> D["Create 10 BTC<br>Locked Position Trade Set"]
    D --> E[Lock for Trading]
    E --> F["Update Lock Type:<br>ASSET → TRADE"]
    F --> G["Remove 10 BTC<br>Locked Position Trade Set"]
    G --> H{"Normal Trade Set<br>Exists?"}
    H -->|No| I[Create Normal Trade Set]
    H -->|Yes| J[End]
    I --> J

    style B fill:#f9f,stroke:#333,stroke-width:2px
    style C fill:#bbf,stroke:#333,stroke-width:2px
    style D fill:#f96,stroke:#333,stroke-width:2px
    style E fill:#bbf,stroke:#333,stroke-width:2px
    style F fill:#bfb,stroke:#333,stroke-width:2px
    style G fill:#f96,stroke:#333,stroke-width:2px
    style H fill:#fcf,stroke:#333,stroke-width:2px
    style I fill:#f96,stroke:#333,stroke-width:2px
```

</div>

#### Unlocked scenario

##### 1. Unlocked for trading
- User can add or close on this symbol normally with normal trade set

##### 2. Unlocked for asset

<div align="center">

```mermaid
flowchart TD
    A[Start] --> B[Open 10 BTC Position]
    B --> C[Lock for Asset]
    C --> D["Create 10 BTC<br>Locked Position Trade Set"]
    D --> E[Unlock for Asset]
    E --> F["Keep Locked Position Trade Set"]
    F --> G[Close All Positions]
    G --> H["Close Locked Position<br>PnL Counted to Investor"]
    H --> I["Close Normal Trade Set<br>Exclude Locked Symbol<br>for Asset"]
    I --> J[End]

    style B fill:#f9f,stroke:#333,stroke-width:2px
    style C fill:#bbf,stroke:#333,stroke-width:2px
    style D fill:#f96,stroke:#333,stroke-width:2px
    style E fill:#bbf,stroke:#333,stroke-width:2px
    style F fill:#bfb,stroke:#333,stroke-width:2px
    style G fill:#f96,stroke:#333,stroke-width:2px
    style H fill:#fcf,stroke:#333,stroke-width:2px
    style I fill:#f96,stroke:#333,stroke-width:2px
```
</div>



#### Dependencies and Integration
NONE

## Drawbacks

Need to update retrieve base on lock type


## Alternatives

## Adoption and Migration Strategy

### Implementation Plan

1. Migrate DB for locked_positions and locked_position_histories
2. Update API endpoint
3. Update FE to help user can interaction
4. Update account trade set worker can define when close normal trade set and how to calculate pnl
5. Update retrieve trade set script

### Migration

- Schema **locked_positions**
  - add `type` varchar (ASSET | TRADING)
  - add `qty` decimal(20,8)

- Schema **locked_position_histories**
  - add `type` varchar (ASSET | TRADING)
  - add `qty` decimal(20,8)
  - `action` has more `MODIFY` value

### Documentation and Education
N/A

## Definition of Success

- User can know which lock type of locked position and can lock, unlock, and change type
- System can calculate correct PnL separately between trading and holding asset

## Unresolved Questions

In FE which solution we allow
1. Have to unlock before lock other type
2. User can change type directly while locking position

## Future Possibilities
N/A
