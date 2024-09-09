
# Chapter-wise questions

## 01_1_Introducing_Bitcoin

This chapter covers the conceptual overview of the Bitcoin System. While it's not exhaustive, it provides the rudimentary details
to understand Bitcoin and its transactions.

Following are some questions to be discussed.

 - Describe in brief the main components of the Bitcoin system. What are transactions? How are they created? How are they Protected?

 - What are cryptographic primitives used in Bitcoin? Give a brief description of them.

 - What is the use of the Elliptic Curve in Bitcoin? What's the name of the elliptic curve used in Bitcoin? Are there other elliptic curves? Bonus: Why was this particular curve selected for Bitcoin?

*  - What is a Blockchain? What makes it different from an Array or other common data types in programming? When is Blockchain data structure useful?

 - Describe in Brief what Lightning Network is. What is the main benefit of using the Lightning network?

 - What makes Bitcoin different from conventional payment systems? Why is this necessary?


 ## 02_0_Setting_Up_a_Bitcoin-Core

 This chapter describes different ways of setting Bitcoin Core in your system. If you are on linux/mac we recommend installing and running Bitcoin Core on your local machine.

 Follow the local installation guide here: https://github.com/BlockchainCommons/Learning-Bitcoin-from-the-Command-Line/blob/master/A2_0_Compiling_Bitcoin_from_Source.md

 If you are using Windows, we recommend setting up Bitcoin Core in a VPS, following the guide here: https://github.com/BlockchainCommons/Learning-Bitcoin-from-the-Command-Line/blob/master/02_1_Setting_Up_a_Bitcoin-Core_VPS_with_StackScript.md

 Below are few general questions to discuss on the initial setup:

 - What is a software signature? Why is it recommended to verify the signature of the downloaded Bitcoin Core binary? What possible attack can be made with a malicious binary?
 - Why is it required to install an old version of BDB to run Bitcoin? What happens when you don't install BDB and try to run the software?
 - Whats the difference between bitcoind and bitcoin-qt? When to use one over the other?
 - What are the different self-hosted node setup? Have you used any of them? Which one have you found most user-friendly?
* - Why is it important to run your own Bitcoin node?
 - What does `autogen`.sh` and `configure` does while building bitcoin core from source?


# 03_0_Understanding_Your_Bitcoin_Setup

 - What is `bitcoin-cli`? What happens when you run `bitcoin-cli` command without starting `bitcoind`?
 - Whats the difference between different node types, ex: mainnet, testnet, signet, and regtest?
 - What is `bitcoin.conf` file? Where is it located? What is it used for?
 - What do the folder `blocks` and `chainstate` contains in the Bitcoin data directory?
 - Explain the use of the following `bitcoin-cli` commands:
    - `getblockchaininfo`
    - `getmininginfo`
    - `getnetworkinfo`
    - `getnettotals`
    - `getwalletinfo`
 - What are the different address types used in Bitcoin? What is a `legacy` address?
 - What is a Segwit address? Why should segwit address be preferred over a legacy address?
 - What is a bitcoin faucet? Why is it only available for testnet and signet? How to get coins in regtest?
 - What is a Transaction Id? What other `bitcoin-cli` calls are there that take in a `txid`? Why are `txid`s useful?
 - What is a descriptor? What is it useful for?

# 04_0_Sending_Bitcoin_Transactions

 - What are the components of a transaction structure? Describe in brief each component and the data they contain.
 - What is the transaction fee? Why a transaction has fees? How to determine a suitable fee at the time of transaction creation?
 - What is an unspent transaction output? How does `bitcoind` select utxos in case of `sendtoaddress` call?
 - What does the confirmation of a transaction indicate? Why should we wait for a certain confirmation number on a transaction before spending them?
 - What is a change address? What happens if we don't put the change address in `createrawtransaction` call?
 - What is the difference between `createrawtransaction` and `fundrawtransaction` call? When to use one over the other?
 - What is the difference between a segwit and a normal transaction?


# 05_0_Controlling_Bitcoin_Transactions

 - What is sequence number? What are the different ways it can be used to lock transactions?
 - What is RBF? What is it useful for?
 - What is CPFP? When to use it instead of RBF? Does RBF change TXid? If so, why?
 - What are some practical use cases of CPFP (hint: Lightning anchor outputs in channel opening transactions)
 - What happens when a transaction being bumped by CPFP also gets RBF'd at the same time? What happens to the child transaction?

# 06_0_Expanding_Bitcoin_Transactions_Multisigs

 - What is a multisig? What are the common script types for multisig addresses?
 - Why is it important to preserve the order of keys in multisig addresses for address generation? What happens if the order isn't preserved?
 - What is BIP67 lexicographical ordering?
 - Does the order of signature matter for signing multisig?
 - Explain the use of `addmultisigaddress` command. When is it useful over vanilla multisig generation?


# 07_0_Expanding_Bitcoin_Transactions_PSBTs

 - What is a PSBT and why is it useful?
 - What are the different components of PSBT? Can you explain each part and it's use in brief?
 - What is HWI? What it is useful for?


# 08_0_Expanding_Bitcoin_Transactions_Other
 - How locktime via unix time and via blockheight are differentiated from the transaction data? [extra resources]
 - What is a LockTime? Why locktimes are useful?
 - What is OP_RETURN? How are the useful? What happens in script verification when when it encounters an OP_RETURN?

# 09_0_Introducing_Bitcoin_Scripts

 - What is ScriptPubkey and ScriptSigs? How they are used in the script verification?
 - Why P2PKH is needed when we already had P2PK. [Extra reading resources]
 - Describe the difference between Segwit and NonSegwit Script verification.
 - How is a ScriptPubkey reduced into an Address? Can you recover a ScriptPubkey from an Address?
 - What are standard and nonstandard script_pubkeys? Can you create an submit a transaction with nonstandrd pubkey to you mempool? [Hint: Create a transaction with addition script, call testmempoolaccept].
 - How can you broadcast a non-standard reedemscript?

# 10_0_Embedding_Bitcoin_Scripts_in_P2SH_Transactions

 - Describe the script verification mechanism of P2SH.
 - Why P2SH is useful when we can have the raw locking script inside the script_pubkey?
 - Why P2SH hash length is 20 bytes, where as P2WSH script hash is 32 bytes? [extra resource]
 - Why does multisig reedemscript start with a `0`?  Is this a bug? Is there a to fix it?
 - What is the reason for wrapping P2WSH inside a P2SH?


# 11_0_Empowering_Timelock_with_Bitcoin_Scripts

 - What are the limitations of nLockTime?
 - What is the difference between relative and absolute locktime?
 - How are sequqence locks are set in a transaction? What was the previous (intended) use case of this data in the transaction?
 - Describe in brief how CLTV verification works.
 - Describe in brief how CSV verification works.
 - What happens when a transaction includes both nlocktime and nsequqnce values? What is the error in testmempool accept when using a transaction like that.

# 12_0_Expanding_Bitcoin_Scripts
 - How can script conditionals cause transaction malleability? [wizard]
 - What are some real world conditional script examples?
 - What are some practical examples of OP_SWAP?

# 13_0_Designing_Real_Bitcoin_Scripts
 - What can multisig escrows be useful for?
 - What are some real world exmaple of Multisig escrows?
 - Is there any real world examples of complex bare scripts?
 - What is the size constraints of Bitcoin reedemscripts?


# General Extra Resource Questions:
 - Standardness Rules.
   - Why having bigger mempool is actually a bad idea?
   -
 - Coinselection.
 - Descriptors.
 - Taproot.
 - RBF/CPFP.
 - Relay Policies.
 - Blockchain, blockheaders, related RPCs.
 - P2P and related RPCs.

# Wizard Questions
 -

# Exercises

 - Week 2: Installation, Setting up, Running the wallet.
 - Week 3: Transaction creation + RBF/CPFP.
 - Week 4: Multisig + PSBT.
 - Week 5: Locktime, OP_RETURN, P2PKH/P2WPKH Scripts.
 - Week 6: Locktime + P2SH/P2WSH(nested).
 - Week 7: Conditionals and puzzle scripts.

