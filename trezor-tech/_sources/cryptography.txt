Cryptography
============

TREZOR adheres to current advanced cryptography standards.  Many of these standards are published as `BIPs <https://github.com/bitcoin/bips>`_ or Bitcoin Improvement protocols.  This page documents which standards TREZOR uses.

Mnemonic recovery seed (`BIP39 <https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki>`_)
--------------------------------------------------------------------------------------------------

`BIP39 <https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki>`_ - used to manage your recovery seed and recovery words.

    **Abstract**
    
    This BIP describes the implementation of a mnemonic code or mnemonic sentence -- a group of easy to remember words -- for the generation of deterministic wallets.
    
    It consists of two parts: generating the mnemonic, and converting it into a binary seed. This seed can be later used to generate deterministic wallets using `BIP-0032 <https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki>`_ or similar methods.

    **Motivation**
    
    A mnemonic code or sentence is superior for human interaction compared to the handling of raw binary or hexadecimal representations of a wallet seed. The sentence could be written on paper or spoken over the telephone.
    
    This guide meant to be as a way to transport computer-generated randomness over human readable transcription. It's not a way how to process user-created sentences (also known as brainwallet) to wallet seed.

Your TREZOR uses a mnemonic that is between 12 and 24 words.  These mnemonics correspond to recovery seeds of the following size:

=============== ==== ==== ====
Word count      12   16   24
=============== ==== ==== ====
Seed size       128  192  256
--------------- ---- ---- ----
Checksum bits   4    6    8
--------------- ---- ---- ----
Total bit width 132  198  264
=============== ==== ==== ====

In order to convert a binary seed to a mnemonic, the full seed, along with its checksum, is broken into 11bit segments.  Each of these segments is represented by one of the 2048 words from the TREZOR's mnemonic seed dictionary.

Passphrase encryption
---------------------

TREZORs passphrase encryption is implemented as part of BIP 39.  It allows for advanced features such as using `multiple hidden volumes <../trezor-user/advanced_settings.html>`_ with your TREZOR.

Hierarchical Deterministic wallets (`BIP32 <https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki>`_ and `BIP44 <https://github.com/bitcoin/bips/blob/master/bip-0044.mediawiki>`_)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

TREZOR uses a Hierarchical Deterministic wallet(HD Wallet for short.  Using an HD Wallet allows your TREZOR to manage multiple bitcoin accounts with multiple addresses while still being recoverable with a simple 12-24 word seed.

`BIP32 <https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki>`_ - the cryptography behind how TREZOR generates the keys for your bitcoin accounts from the recovery seed.

    **Abstract**
    
    This document describes hierarchical deterministic wallets (or "HD Wallets"): wallets which can be shared partially or entirely with different systems, each with or without the ability to spend coins.
    
    The specification is intended to set a standard for deterministic wallets that can be interchanged between different clients. Although the wallets described here have many features, not all are required by supporting clients.
    
    The specification consists of two parts. In a first part, a system for deriving a tree of keypairs from a single seed is presented. The second part demonstrates how to build a wallet structure on top of such a tree.

    **Motivation**
    
    The Bitcoin reference client uses randomly generated keys. In order to avoid the necessity for a backup after every transaction, (by default) 100 keys are cached in a pool of reserve keys. Still, these wallets are not intended to be shared and used on several systems simultaneously. They support hiding their private keys by using the wallet encrypt feature and not sharing the password, but such "neutered" wallets lose the power to generate public keys as well.
    
    Deterministic wallets do not require such frequent backups, and elliptic curve mathematics permit schemes where one can calculate the public keys without revealing the private keys. This permits for example a webshop business to let its webserver generate fresh addresses (public key hashes) for each order or for each customer, without giving the webserver access to the corresponding private keys (which are required for spending the received funds).
    
    However, deterministic wallets typically consist of a single "chain" of keypairs. The fact that there is only one chain means that sharing a wallet happens on an all-or-nothing basis. However, in some cases one only wants some (public) keys to be shared and recoverable. In the example of a webshop, the webserver does not need access to all public keys of the merchant's wallet; only to those addresses which are used to receive customer's payments, and not for example the change addresses that are generated when the merchant spends money. Hierarchical deterministic wallets allow such selective sharing by supporting multiple keypair chains, derived from a single root.

`BIP44 <https://github.com/bitcoin/bips/blob/master/bip-0044.mediawiki>`_ - the hierarchy of the keys generated by TREZOR.

    **Abstract**
    
    This BIP defines a logical hierarchy for deterministic wallets based on an algorithm described in BIP-0032 (BIP32 from now on) and purpose scheme described in `BIP-0043 <https://github.com/bitcoin/bips/blob/master/bip-0043.mediawiki>`_  (BIP43 from now on).
    
    This BIP is a particular application of BIP43.

    **Motivation**
    
    The hierarchy proposed in this paper is quite comprehensive. It allows the handling of multiple coins, multiple accounts, external and internal chains per account and millions of addresses per chain.

Secure transactions
-------------------

TREZOR and the myTREZOR wallet work in concert in order to conduct secure, zero trust, transactions.  In order to construct a transaction, the myTREZOR wallet sends TREZOR a list of incoming transactions and a list of outgoing addresses with amounts.  TREZOR then verifies that the incoming transactions were valid, and that they contain the right amount of bitcoins in order to send to the outgoing addresses.  Your TREZOR will also ask you before sending any money anywhere.  Once a transaction is confirmed by the user, TREZOR constructs a new transaction and sends it back to myTREZOR.   This transaction is in turn verified by myTREZOR to be correct.  This ensures that no single malfunction of the system could lead to your bitcoins getting sent to the wrong address.
