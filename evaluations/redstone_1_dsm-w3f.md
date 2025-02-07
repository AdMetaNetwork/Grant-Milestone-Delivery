# Evaluation

- **Status:** In Progress
- **Application Document:**  https://github.com/w3f/Grants-Program/blob/master/applications/RedStone%20Network.md 
- **Milestone:** 1
- **Kusama Identity:** Address
- **Previously successfully merged evaluation:** N/A

| Number | Deliverable | Accepted | Link | Evaluation Notes |
| ------ | ----------- | -------- | ---- |----------------- |
| 0a.    | License                         |<ul><li>[x] </li></ul>| [Apache 2.0](https://github.com/redstone-network/redstone-node/blob/main/LICENSE) |                                                              |
| 0b.    | Documentation                   |<ul><li>[ ] </li></ul>| [https://github.com/redstone-network/redstone-node#run-the-rsn-node](https://github.com/redstone-network/redstone-node#run-the-rsn-node) |  |
| 0c.    | Testing Guide                   |<ul><li>[ ] </li></ul>| [https://github.com/redstone-network/redstone-node#run-tests](https://github.com/redstone-network/redstone-node#run-tests) | Tests are not running. |
| 0d.    | Article/Tutorial                |<ul><li>[ ] </li></ul>| [https://github.com/redstone-network/redstone-node#module-documentation](https://github.com/redstone-network/redstone-node#module-documentation) | Need beter tutorial/article |
| 1a.    | Substrate module: Defense    |<ul><li>[ ] </li></ul>| [	https://github.com/redstone-network/redstone-node/tree/main/pallets/defense](	https://github.com/redstone-network/redstone-node/tree/main/pallets/defense) | Not evaluated yet. |
| 1b.    | Substrate module: Notification     |<ul><li>[ ] </li></ul>| [https://github.com/redstone-network/redstone-node/tree/main/pallets/notification](https://github.com/redstone-network/redstone-node/tree/main/pallets/notification) | Not evaluated yet. |
| 1c.    | Substrate module: Permission-capture |<ul><li>[ ] </li></ul>| [https://github.com/redstone-network/redstone-node/tree/main/pallets/permission-capture](https://github.com/redstone-network/redstone-node/tree/main/pallets/permission-capture) | Not evaluated yet. |
| 2.     | Docker                          |<ul><li>[ ] </li></ul>| [https://github.com/redstone-network/redstone-node#run-in-docker](https://github.com/redstone-network/redstone-node#run-in-docker) | Problem to access the service |


## General Notes

### Testing Guide

I was able to compile the code with `cargo build --release`, however the tests `cargo test --release` are failing to compile with the following error:

```
error[E0046]: not all trait items implemented, missing: `TransferProtectInterface`
  --> open-runtime-module-library/currencies/src/mock.rs:76:1
   |
76 | impl orml_tokens::Config for Runtime {
   | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ missing `TransferProtectInterface` in implementation
   |
   = help: implement the missing item: `type TransferProtectInterface = Type;`

For more information about this error, try `rustc --explain E0046`.
error: could not compile `orml-currencies` due to previous error
warning: build failed, waiting for other jobs to finish...
error[E0046]: not all trait items implemented, missing: `TransferProtectInterface`
   --> open-runtime-module-library/tokens/src/mock.rs:272:1
    |
272 | impl Config for Runtime {
    | ^^^^^^^^^^^^^^^^^^^^^^^ missing `TransferProtectInterface` in implementation
    |
   ::: open-runtime-module-library/tokens/src/lib.rs:239:9
    |
239 |         type TransferProtectInterface: TransferProtectInterface<Self::Balance>;
    |         ---------------------------------------------------------------------- `TransferProtectInterface` from trait                                                                                                

error: could not compile `orml-tokens` due to previous error
```

When I tried to spin up the blockchain node, as describedd [here](https://github.com/redstone-network/redstone-node#run-the-rsn-node), I notice that the executable did not exist. The files in the target folder are listed in the image below. Can you provide assistence on that?

![image](https://user-images.githubusercontent.com/112647953/205960416-290b6101-4362-44cf-9a88-4e77b4b9cf46.png)


### Article/Tutorial 

We need better explanation on how to test the behavior or the system, as a sequence of steps on how to use these features in the blockchain.

### Docker

From docker I was able to spin up the node but I cannot connect to it using default port (9944) on Polkadot.js. 

### Code quality

Not evaluated yet. 

