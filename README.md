# Lightweight Beaconchain Explorer

<b>This is a work in progress project!\
It's not ready to be used in any way yet.</b>

## What is this?
This project is planned to become a lightweight beaconchain explorer.

A Beaconchain explorer is a tool that allows users to view and interact with the data on the Ethereum Beacon Chain. It is similar to a blockchain explorer, which allows users to view data on a blockchain such as the current state of transactions and blocks - but focussed on exploring the beaconchain.

This "lightweight" explorer is planned to proxy most of the queries to an underlying standard beacon node api, which makes it a lot easier and cheaper to run (no 3rd party proprietary database like bigtables required)

## Background
https://github.com/ethpandaops/tooling-wishlist/blob/master/tools/lightweight-beaconchain-explorer.md

## TODO

(More for myself to keep track of what is done / needs to be done)

* [ ] Explorer Pages (UI)
  * [ ] Layout polishing
  * [ ] Startpage
  * [ ] Epoch Overview (`/epochs`)
  * [ ] Slots Overview (`/slots`)
  * [x] Slot details (`/slot/{slot_or_root}`)
    * [ ] Enhance view controls (Hex/UTF8 Grafitti, Local/UTC Time, Copy Buttuns etc.)
  * [ ] Search (Block Root, Epoch Number, Slot Number, Grafitti)
    * [ ] Type-Ahead search
* [ ] RPC Client / Caching
  * [x] Get Block Header by slot / block root
  * [x] Get Block Body by block root
  * [x] Get Epoch assignments (proposer, attester & sync committee duties)
    * [x] Simple cache for epoch duties
    * [ ] Persistent cache for epoch duties in DB
* [ ] Database
  * [ ] Schema initialization / upgrade
  * [ ] Table: Blocks (Slot index for search & slot overview)
  * [ ] Table: Epochs (Epoch index for startpage & epoch overview)
  * [ ] Table: SyncState (keeps track of synchronization state for Blocks & Epochs indexes)
* [ ] Indexer
  * [x] Keep track of current & last epoch in memory
  * [ ] Aggregate Votes
  * [ ] Update Slot index in DB
  * [ ] Update Epoch index in DB
  * [ ] Synchronization (index older epochs)
