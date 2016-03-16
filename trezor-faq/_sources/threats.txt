Security threats
%%%%%%%%%%%%%%%%

What happens if my TREZOR gets stolen?
======================================

- Can the thieves take all my coins?
- Is there some way to recover my account once I get a new TREZOR?

The short answers:

- No. Each TREZOR has a `PIN code <http://doc.satoshilabs.com/trezor-user/enteringyourpin.html>`_ to prevent misuse in case of physical thief.
- Yes. See `recovery <http://doc.satoshilabs.com/trezor-user/recovery.html>`_.

Just how easy (or hard) is it to get some bitcoins out of a stolen TREZOR?


Brute forcing the TREZOR PIN
----------------------------

Your TREZOR is protected by a PIN code, which can be up to 10 digits between 1 and 9.  There are 6561 possible 4 digit PINs for the TREZOR.  If you choose a good PIN, it will take hundreds to thousands of guesses to guess your PIN.  Each time you enter a wrong PIN, the wait time increases by a power of 2.  After the first few failures, you have to wait several seconds before you'll be able to try another PIN.  Even just trying the `top 20 PINs <http://www.datagenetics.com/blog/september32012/>`_ would take about 6 days(150 hours). Trying 30 PINs would take around 17 years.  Trying 100 random PINs would take a VERY LONG time.

The number of PIN entry failures is stored in the TREZOR's memory.  This means that power cycling the TREZOR won't magically make the wait time go to zero again.  The best you can do by turning the TREZOR on and off again is make the timer start over again.


Reflashing the TREZOR with evil firmware
----------------------------------------

Official TREZOR firmware is signed by the SatoshiLabs master key.  Installing unofficial firmware on the TREZOR is possible, but doing so will wipe the device storage and TREZOR will show a warning every time it starts.  Reprogramming the bootloader is impossible, because all TREZORs ship with their secure programming fuse blown.


Inspect the TREZORs memory with an electron microscope
------------------------------------------------------

You might imagine yourself `dissolving the TREZOR CPU in acid <http://zeptobars.ru/en/read/OPA627-AD744-real-vs-fake-china-ebay>`_, finding the reprogramming fuse, repairing it, and then loading evil firmware on the TREZOR.  I'm no science fiction author, but my guess is -- this might be possible.  However, the Cortex M3 is a sensitive multilayer chip.  The components inside are much smaller than those fake eBay amps.  Chances are, all you'd end up doing is destroying the chip.  Even if you succeeded in doing so, this will be a costly and time consuming task.  In the end the bitcoins will be gone already because the original owner will have `changed their recovery seed <http://doc.satoshilabs.com/trezor-user/advanced_features.html#changing-your-trezor-recovery-seed>`_ upon discovering that their TREZOR was stolen.


Evil maid attack - replace the TREZOR with a fake
-------------------------------------------------

It might be possible for an evil ninja, or your little brother, to steal your TREZOR and replace it with a fake TREZOR.  If the fake TREZOR was embedded with a wireless transmitter, then the fake TREZOR could wirelessly transmit any PIN it received.   The attacker would then have full access to your funds.

If you are concerned about such an attack, it is a good idea to sign the back of your TREZOR with a permanent pen. Don't forget to check the signature before each use.

The TREZOR's chassis is sealed using ultrasound. Opening the TREZOR without destroying the case is nearly impossible.


What if my computer that runs my bitcoin wallet is stolen?
==========================================================

If your computer gets stolen, just plug your TREZOR to another computer and you'll get your account balance and transaction history. Might your TREZOR get lost as well, simply recover the seed from your paper backup to a new TREZOR device or a TREZOR compatible wallet software. 


What happens if my recovery seed is stolen?
===========================================

You need to keep your recovery seed safe from theft.  If your recovery seed is stolen and you haven's set a passphrase protection, then your bitcoins can be stolen as well.  However, if you like, TREZOR can protect against recovery seed theft with `a passphrase <../trezor-user/advanced_settings.html#using-passphrase-encrypted-seeds>`_, and therefore eliminate this risk.


What happens if the SatoshiLabs servers are hacked and the firmware signing key is stolen?
==========================================================================================

First off, this won't happen ;).  The SatoshiLabs master key is kept very safe.  However, you don't need to rely on the SatoshiLabs signature.  You can `verify the build yourself <https://github.com/trezor/trezor-mcu/blob/master/README.rst>`_.  Our hope is that a few trusted TREZOR users will make a habit of verifying firmware checksums.  If you are concerned about this, we suggest making a habit of checking `our blog <http://satoshilabs.com/news>`_ or social news channels such as `reddit <http://www.reddit.com/r/TREZOR>`_ before applying any updates.  If there ever was a problem with the firmware not matching the source code, you can be sure someone will have written about it.

You don't need to worry about the firmware being updated by a computer virus.  Your TREZOR will ask you to manually confirm the update before anything is written to the TREZOR's memory.


What happens if the SatoshiLabs shuts down?
===========================================

There are no such plans because we love bitcoin, but even if we had to close down, there's nothing to worry about. 
You can use your TREZOR together with other BIP32, BIP39 and BIP44 `compatible wallets <../trezor-apps/index.html>`_. Since our code is opensource, developers from around the world can maintain it and add new functionalities.


What if I run the TREZOR recovery process on an infected computer?
==================================================================

During `the TREZOR recovery process <../trezor-user/recovery.html>`_ you are asked to enter your recovery seed into the computer with the words in a random order.  By default, the TREZOR uses a 24 word recovery seed.

If your computer has a keylogger installed on it, then the randomly ordered words may be stolen. One might try to re-arrange these words, until they found the correct word ordering.  They can check the order of the words, by generating a bitcoin address using each ordering and checking if the address belongs to you.

There are `24! <http://en.wikipedia.org/wiki/Factorial>`_ possible orderings of a 24 word seed.  That is 620448401733239439360000 possible orderings.

Each 24 word TREZOR recovery seed is verified with an `8 bit checksum <../trezor-tech/cryptography.html#mnemonic-recovery-seed-bip39>`_ .  Using the checksum to eliminate invalid seeds, you can reduce the search space by a factor of 256.  This gives us a search space of:

24! ÷ 256 = 2423626569270466560000

Going from TREZOR recovery seed to public bitcoin address takes 2 × 2048 iterations of `PBKDF2 <https://en.wikipedia.org/wiki/PBKDF2>`_, which in turn uses `SHA-512 <https://en.wikipedia.org/wiki/SHA-512>`_. All in all, going from a potential TREZOR recovery seed to a bitcoin address, is slightly more difficult than running SHA-512 8096 times.

To summarise, in order to check all possible orderings in a 24 word seed, you need to run SHA-512:

24! ÷ 256 × 8096 = 19621680704813697269760000 times

The bitcoin network is capable of preforming `176 537 883 000 000 000 <https://blockchain.info/charts/hash-rate>`_ iterations of `SHA-256 <https://en.bitcoin.it/wiki/Hash>`_ each second.

If we wave our hands a bit, we can claim that SHA-512 and SHA-256 are the same difficulty (which they aren't but let's pretend they are).  Therefore, it should take somewhere around half of:

(24! ÷ 256 × 8096) ÷ 176 537 883 000 000 000 ÷ 60 ÷ 60 ÷ 24 ÷ 365 = 3.5 years

for the **ENTIRE BITCOIN NETWORK** to crack the seed.  If you have that kind of hashing power, you'd make better money mining at `Slush Pool <https://mining.bitcoin.cz/>`_ than trying to steal bitcoins. :-) On a normal botnet cracking a TREZOR seed would take millenia.


What doesn't TREZOR protect against (yet)?
==========================================

Phishing
--------

If you wish to make a payment to someone on the Internet, you need to know their bitcoin address. Unlike TREZOR, computers are not necessarily secure and it is possible that the bitcoin address displayed on your screen has been maliciously modified.

To be safe, we recommend confirming the recipient's bitcoin address through a second channel, such as SMS, a phone call, or an in-person meeting.

When **receiving funds**, you can guarantee that you are providing safe receiving addresses by using the `Show on TREZOR <../trezor-user/receivingpayments.html#receiving-payments>`_ feature. Using this feature you can easily check to see if the receiving address has not been changed on a potentially compromised computer.
