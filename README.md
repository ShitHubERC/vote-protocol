# vote-protocol

A simple smart contract which only records everyone’s voting on each proposal.

## Design

This voting smart contract has no admin privilege. It is only used to record the vote(for/against) of the community members on the blockchain. Because the voting smart contract is simple enough and can not change anything of ShitHub directly, we could audit it by the community only.

A proposal has the following on-chain metadata:

```
id: auto-increment unique id
proposal link: the forum link of the proposal
active time: [begin block, end block] for voting
```

The smart contract has the following public functions:

```
propose(link, begin, end): Create a new proposal, need a proposal privilege
vote(id, for/against): Vote for/against the proposal with id
```

The smart contract has the following events:

```
Proposal(id, link, begin, end): The new proposal is created.
Vote(address, id, for): Someone changes his/her vote on the proposal.
```

The backend system can use the events to trace the voting.

However, anyone can verify the voting result by reading this contract’s data from block-chain. Nobody can cheat on voting.

## Deployed Contracts

VoteBox
[0x41747066aE85B73ac5f868A6cFCA55A01A0ccDC6](https://rinkeby.etherscan.io/address/0x41747066ae85b73ac5f868a6cfca55a01a0ccdc6#code)
