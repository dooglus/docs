Software design & security
==========================

What is a recovery seed, a PIN and encryption passphrase and the difference between them?
-----------------------------------------------------------------------------------------

**Recovery seed** is a mnemonic code made of 12, 18 or 24 words depending on your choice. This seed is generated the first time you run TREZOR and will help you recovering it's contents (private keys, bitcoin balance and transaction history) into a new device if you lose your TREZOR. 

**PIN** is a number that you set when you first run TREZOR. It protects TREZOR against being used by unauthorized persons. We have invented a `secure way <../trezor-user/enteringyourpin.html>`_ of entering the PIN so it can’t be keylogged and misused.

**Encryption passphrase** can be set on top of the PIN. This protects the device in case of seizure. It's using military-grade encryption of the seed on TREZOR storage, so even torturing the device in a laboratory won't leak your private keys.

A combination of these security mechanisms makes your bitcoin ownership with TREZOR absolutely safe.


Is it safe to enter the PIN on my computer and not on the TREZOR itself?
------------------------------------------------------------------------

TREZOR doesn't have a keyboard but even if you enter the PIN on the computer directly, you're perfectly safe. TREZOR's PIN mechanism is protected against key-loggers, so using it even in internet cafes means no risk for you.


Why should I trust TREZOR with my private keys?
-----------------------------------------------

Because the entire software design of TREZOR is open-source. You can verify the product by yourself or find some other professional you trust to do so. 

You can find all the repositories `here <../trezor-tech/resources.html>`_.


How can a seed made of several simple words be more secure than a strong password with caps or numerical signs?
---------------------------------------------------------------------------------------------------------------

We love this picture, it explains it all:

.. image:: images/password_strength.png

Comic by `XKCD: Randall Munroe <http://xkcd.com/>`_, licensed under `Creative Commons Attribution-NonCommercial 2.5 License <http://creativecommons.org/licenses/by-nc/2.5/>`_.


Why should I do a paper backup of my seed?
------------------------------------------

We think paper backups are the easiest and safest way of storing such information for a common computer user. Computer backups on the contrary are vulnerable to hardware damage and subject to frequent hacker attacks.


If somebody steals my Trezor, they'll just empty out my wallet before I have the chance to restore anyway. Right?
-----------------------------------------------------------------------------------------------------------------

Not at all. All operations on TREZOR require the user to enter a **PIN**. The attacker would have to guess your PIN which is very difficult because with each badly entered PIN the time for entering it anew increases exponentially. For example, the delay between 19th and 20th PIN entering is 35 hours. Unplugging and plugging the device won’t help. The thief would have to sit his life off entering the PINs. Meanwhile you have enough time to move your funds into a new device or wallet from the paper backup.

You can also hide your wallet behind **passphrase** which can be set on top of the PIN. Read more about the `multi-passphrase encyption (hidden wallets) <../trezor-user/advanced_settings.html#multi-passphrase-encryption-hidden-wallets>`_.
