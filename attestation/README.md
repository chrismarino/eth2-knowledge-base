---
description: Attestation Inclusion delay and why it is important
---

# Attestation

This post will use [AttestantIO](https://twitter.com/attestantio)'s post about [_Attestation effectiveness_](https://www.attestant.io/posts/defining-attestation-effectiveness/) as a reference.

## General

#### Attestation 

Every [Epoch](https://kb.beaconcha.in/glossary#epoch) \(~6.4 minutes\) a validator proposes an attestation \(vote\) to the network.  
This vote consists of the following segments:

* [Committee](https://kb.beaconcha.in/glossary#slots)
* [Validator Index](https://kb.beaconcha.in/glossary#unique-index)
* Finality vote
* Signature
* Chain head vote \(vote on what the validator believes is the head of the chain\) 

A minimum of 16,384 validators is required to start Ethereum 2.0.   
If we multiply that with the information included in each Attestation per Epoch, it adds up quickly. Therefore, Ethereum 2.0 **aggregates** all of that information and minimises the data growth.  


#### Aggregated Attestation

> An [aggregation](https://www.vocabulary.com/dictionary/aggregation) is a collection, or the gathering of things together. Your baseball card collection might represent the aggregation of lots of different types of cards.

So what does that mean for Attestations?  
  
Each block one or more committees are chosen to attest. A committee has a minimum of 128 validators, of which 16 are randomly selected to become an aggregator.  
As shown below, the validators send their unaggregated attestation to the aggregators. They then merge the attestations and forward a single aggregated attestation to the [block proposer](https://github.com/gobitfly/eth2-beaconchain-explorer/pull/218).

![](../.gitbook/assets/image%20%28164%29.png)


