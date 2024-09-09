
# Chapter-wise questions

## 01 Introducing Bitcoin

This chapter covers the conceptual overview of the Bitcoin System. While it's not exhaustive, it provides the rudimentary details
to understand Bitcoin and its transactions.

Following are some questions to be discussed:
 - Describe in brief the main components of the Bitcoin system. What are transactions? How are they created? How are they protected?
 - What are cryptographic primitives used in Bitcoin? Give a brief description of them.
 - What is the use of the Elliptic Curve in Bitcoin? What's the name of the elliptic curve used in Bitcoin? Are there other elliptic curves? Bonus: Why was this particular curve selected for Bitcoin?
 - What is a blockchain? What makes it different from an array or other common data types in programming? When is blockchain data structure useful?
 - What is the Lightning Network? What is the main benefit of using the Lightning network?
 - What makes Bitcoin different from conventional payment systems? Why is this necessary?


## 02 Setting Up a Bitcoin-Core Node

This chapter describes different ways of setting Bitcoin Core in your system.

If you are on linux/mac we recommend installing and running Bitcoin Core on your local machine. Follow the local installation guide [here](https://github.com/BlockchainCommons/Learning-Bitcoin-from-the-Command-Line/blob/master/A2_0_Compiling_Bitcoin_from_Source.md).

If you are using Windows, we recommend setting up Bitcoin Core in a VPS, following the guide [here](https://github.com/BlockchainCommons/Learning-Bitcoin-from-the-Command-Line/blob/master/02_1_Setting_Up_a_Bitcoin-Core_VPS_with_StackScript.md).

 Below are few general questions to discuss on the initial setup:

 - What is a software signature? Why is it recommended to verify the signature of the downloaded Bitcoin Core binary? What possible attack can be made with a malicious binary?
 - Why is it required to install an old version of BDB to run Bitcoin? What happens when you don't install BDB and try to run the software?
 - Whats the difference between `bitcoind` and `bitcoin-qt`? When to use one over the other?
 - What are the different self-hosted node setup? Have you used any of them? Which one have you found most user-friendly?
 - Why is it important to run your own Bitcoin node?
 - What does `autogen.sh` and `configure` do when building bitcoin core from source?


## 03 Understanding Your Bitcoin Setup

 - What is `bitcoin-cli`? What happens when you run `bitcoin-cli` command without starting `bitcoind`?
 - Whats the difference between different node types (mainnet, testnet, signet, and regtest)?
 - What is `bitcoin.conf` file? Where is it located? What is it used for?
 - What do the folder `blocks` and `chainstate` contains in the Bitcoin data directory?
 - Explain the use of the following `bitcoin-cli` commands:
    - `getblockchaininfo`
    - `getmininginfo`
    - `getnetworkinfo`
    - `getnettotals`
    - `getwalletinfo`
 - What are the different address types used in Bitcoin? What is a `legacy` address?
 - What is a `segwit` address? Why should `segwit` address be preferred over a `legacy` address?
 - What is a bitcoin faucet? Why is it only available for testnet and signet? How to get coins in regtest?
 - What is a transaction id? What other `bitcoin-cli` calls are there that take in a `txid`? Why are `txid`s useful?
 - What is a descriptor? What is it useful for?

## 04 Sending Bitcoin Transactions

 - What are the components of a transaction? Describe in brief each component and the data they contain.
 - What is the transaction fee? Why do transactions need to pay fee? How to determine a suitable fee at the time of transaction creation?
 - What is an unspent transaction output (UTXO)? How does `bitcoind` select UTXOs in case of `sendtoaddress` call?
 - What does the confirmation of a transaction indicate? Why should we wait for a certain confirmation number on a transaction before spending them?
 - What is a change address? What happens if we don't put the change address in `createrawtransaction` call?
 - What is the difference between `createrawtransaction` and `fundrawtransaction` call? When to use one over the other?
 - What is the difference between a segwit and a normal transaction?


## 05 Controlling Bitcoin Transactions

 - What is sequence number? What are the different ways it can be used to lock transactions?
 - What is RBF? What is it useful for?
 - What is CPFP? When to use it instead of RBF? Does RBF change `txid`? If so, why?
 - What are some practical use cases of CPFP (hint: Lightning anchor outputs in channel opening transactions)
 - What happens when a transaction being bumped by CPFP also gets fee bumped by RBF at the same time? What happens to the child transaction?

## 06 Expanding Bitcoin Transactions Multisigs

 - What is a multisig? What are the common script types for multisig addresses?
 - Why is it important to preserve the order of keys in multisig addresses for address generation? What happens if the order isn't preserved?
 - What is BIP67 lexicographical ordering?
 - Does the order of signature matter for signing multisig?
 - Explain the use of `addmultisigaddress` command. When is it useful over vanilla multisig generation?


## 07 Expanding Bitcoin Transactions PSBTs

 - What is a PSBT and why is it useful?
 - What are the different components of PSBT? Can you explain each part and it's use in brief?
 - What is HWI? What it is useful for?


## 08 Expanding Bitcoin Transactions Other
 - How is locktime via unix time and via blockheight are differentiated from the transaction data?
 - What is a LockTime? Why locktimes are useful?
 - What is OP_RETURN? How are the useful? What happens in script verification when when it encounters an OP_RETURN? What if the value of OP_RETURN is non-zero?

## 09 Introducing Bitcoin Scripts

 - What is `scriptpubkey` and `scriptsig`? How they are used in the script verification?
 - Why P2PKH is needed when we already had P2PK?
 - Differentiate between segwit and non-segwit script verification.
 - How is a `scriptpubkey` reduced into an address? Can you recover a `scriptpubkey` from an Address?
 - What are standard and non-standard `scriptpubkeys`? Can you create an submit a transaction with non-standrd `scriptpubkey` to you mempool? [Hint: Create a transaction with addition script, call testmempoolaccept].
 - How can you broadcast a non-standard reedemscript?

## 10 Embedding Bitcoin Scripts in P2SH Transactions

 - Describe the script verification mechanism of P2SH.
 - Why is P2SH useful when we can have the raw locking script inside the `scriptpubkey`?
 - Why is P2SH hash length 20 bytes, where as P2WSH script hash is 32 bytes?
 - Why does multisig `reedemscript` start with a `0`?  Is this a bug? Is there a to fix it?
 - What is the reason for wrapping P2WSH inside a P2SH?

## 11 Empowering Timelock with Bitcoin Scripts

 - What are the limitations of `nLockTime`?
 - What is the difference between relative and absolute time locks?
 - How are sequence locks are set in a transaction? What was the previous (intended) use case of sequence in the transaction?
 - Briefly describe how CLTV verification works.
 - Briefly describe how CSV verification works.
 - What happens when a transaction includes a time lock using both `nlocktime` and `nsequqnce` values? What is the error in `testmempoolaccept` RPC when using a transaction like that.

## 12 Expanding Bitcoin Scripts
 - How can script conditionals cause transaction malleability?
 - What are some real world conditional script examples?
 - What are some practical examples of OP_SWAP?

## 13 Designing Real Bitcoin Scripts
 - What can multisig escrows be useful for?
 - What are some real world example of multisig escrows?
 - Is there any real world examples of complex bare scripts?
 - What is the size constraints of Bitcoin `reedemscript`?


## General Extra Resource Questions:
 - Standardness Rules.
   - Why having bigger mempool is actually a bad idea?
 - Coinselection.
 - Descriptors.
 - Taproot.
 - RBF/CPFP.
 - Relay Policies.
 - Blockchain, blockheaders, related RPCs.
 - P2P and related RPCs.