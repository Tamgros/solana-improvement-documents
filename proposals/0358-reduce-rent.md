---
simd: 'XXXX'
title: Title of SIMD. This should be concise and descriptive.
authors:
  - (fill in with names of authors)
category: Standard/Meta
type: Core/Networking/Interface/Meta
status: Idea/Review
created: (fill me in with today's date, YYYY-MM-DD)
feature: (fill in with feature key and github tracking issues once accepted)
supersedes: (optional - fill this in if the SIMD supersedes a previous SIMD)
superseded-by: (optional - fill this in if the SIMD is superseded by a subsequent
 SIMD)
extends: (optional - fill this in if the SIMD extends the design of a previous
 SIMD)
---

## Summary

It is generally accepted that is too high

## Motivation

Goals
- Lower rent
- Lower it quickly
- Cause minimal disruption to the current ecosystem and future looking proposals

## Dependencies *(Optional)*

As is preferred, this SIMD has no protocol change dependencies.

## New Terminology

No new termonology

## Detailed Design

- Lower Rent!
- Lower it gradually
- Keep the same as a constant, same RPC method. Simple
`SysvarRent111111111111111111111111111111111`


How: We want to lower rent in a principled way
* Undersand what size of snapshot would be problematic
* SOL available ≤ Max_Snapshot_size * Rent_cost
  * ie. The amount of sol available isn't enough to pay for a space that would be problematic
* Reduce it gradually knowing that there isn't enough 

<span style="color:lime">Open discussion</span>
* What is the max_snapshot?


## Alternatives Considered

There are some alternatives under active discussion. This SIMD should be considered in parallel to the solutions that have technical dependencies to implement. 

There was also a SIMD to simply half rent. That is more in line with this proposal, but this proposal intends to be simple, but more principled in approach


[0334-dynamic-state-rent](https://github.com/solana-foundation/solana-improvement-documents/pull/344/files)  
with Related SIMDs
* [0341:v0 Account Compression](https://github.com/solana-foundation/solana-improvement-documents/pull/341) 
* [0329: Track Account Access and Account Creation Slot](https://github.com/solana-foundation/solana-improvement-documents/pull/329)






## Impact

Beyond the obvious reduced friction, this will allow us to understand the elasticity of demand for rent. There are certainly some confounding variables, but incrementally reducing rent will give us some indication on how much it affects account creation relative to other activity on chain

This incremental approach will also allow us to minimize impact of users rushing to dealocate and realocate as users will do this more gadually than with one big change. We can also assess how much this disruption this may cause with the initial changes.

## Security Considerations

The main security imlication is attack vectors around bloating state to the point that snapshots become unweildy. To prevent this negative case, we consider the negative size vs SOL available

## Drawbacks *(Optional)*

The main drawback is this approach doesnt' intorduce any disincentive to dealocate and reallocate an account. This could be disruptive to the ecosystem

## Backwards Compatibility *(Optional)*

