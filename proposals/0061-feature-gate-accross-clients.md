---
simd: 'XXXX'
title: Feature Gate Across Clients
authors:
  - Matt Sorg
category: Standard/Meta
type: Core
status: Draft
created: 2023-07-03
feature: (fill in with feature tracking issues once accepted)
---

## Summary

Add a system for features from all clients to be activated 

## Motivation

As described in the [Feature Gate Setup Process](https://github.com/solana-labs/solana/wiki/Feature-Gate-Setup-Process), any code update that changes whether a specific transaction will successd or fail must fee feature gated.

With more than one client, there is the additional constraint that state transitions must be in sync accross clients. 

### Relevant current process
https://github.com/solana-labs/solana/wiki/Feature-Gate-Setup-Process \
https://github.com/solana-labs/solana/wiki/Feature-Gate-Activation-Process

## Alternatives Considered

<b> Multisig of core contributors controls pub key</b>\
Pros
* Allows for all core contributors to approve a whole feature activation across protocols \

Cons
* Probably requires each contributor to sign for all clients


Feature gates must have a public keys on each client code. 
Activation of a feature is conditional on all gates being active on all clients, so there must\
Pros 
* Granular controls.

Cons 
* Some complexity in coordinating the linked public keys across orgs and repos




## New Terminology

Is there any new terminology introduced with this proposal?

## Detailed Design

Explain the feature as if it was already implemented and you're explaining it
to another Solana core contributor. The generally means:

- Explain the proposed change and how it works
- Where the feature fits in to the runtime, core, or relevant sub-system
- How this feature was/could be implemented
- Interaction with other features
- Edge cases

## Impact

How will the implemented proposal impacts dapp developers, validators, and core contributors?

## Security Considerations

What security implications/considerations come with implementing this feature?
Are there any implementation-specific guidance or pitfalls?

## Drawbacks *(Optional)*

Why should we not do this?

## Backwards Compatibility *(Optional)*

Does the feature introduce any breaking changes? All incompatibilities and
consequences should be listed.

