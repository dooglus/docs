TREZOR Apps
===========

.. image:: images/chapter02.jpg

Except for `myTREZOR <https://mytrezor.com>`_, you can use your TREZOR device with increasing number of independent bitcoin wallets and online services. We call them **TREZOR Apps**:

- `TREZOR Wallets <index.html#using-trezor-with-bitcoin-and-altcoin-wallets>`_
- `Online Services <index.html#using-trezor-with-online-services>`_
- `Recovering Funds <index.html#recovering-funds-without-trezor-device>`_

Using TREZOR With Bitcoin and Altcoin Wallets 
---------------------------------------------

The following **client wallets** let you connect TREZOR and work with it. They don't actually hold any private keys, instead they display balances and help you to manage transactions.

==================================================== ======================== ====================== ====================== ======================= ====================== ======================= ====================== ====================== ====================== ======================
Supported TREZOR features
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Wallet                                               :icon:`cog`              :icon:`life-ring`      :icon:`exchange`       :icon:`users`           :icon:`user-secret`    :icon:`bars`            :icon:`eye-slash`      :icon:`eye`            :icon:`upload`         :icon:`fire`          
`ArcBit <arcbit.html>`_                                                                                                                                                                            ✔                       ✔
`Coinprism <coinprism.html>`_                                                                        ✔                                              ✔                                              
`Copay <copay.html>`_	                                                                             ✔                      ✔                       ✔                      ✔                       ✔                                              
`Chrome Extension <extension.html>`_                 ✔                        ✔                                                                     ✔                                                                                            ✔                      ✔
`Electrum <electrum.html>`_                          ✔                                               ✔                                              ✔                      ✔                       ✔                      ✔
`Electrum-DASH <electrum-dash.html>`_                ✔                                               ✔                                              ✔                      ✔                       ✔                      ✔
`Electrum-LTC <electrum-ltc.html>`_                  ✔                                               ✔                                              ✔                      ✔                       ✔                      ✔
`Encompass <encompass.html>`_                        ✔                                               ✔                                              ✔                      ✔                       ✔                      ✔
`GreenAddress <greenaddress.html>`_	                                                                                        ✔                       ✔                      ✔
`MultiBit HD <multibit.html>`_                       ✔                                               ✔                                                                                             ✔                                                                    ✔                   
`Mycelium <mycelium.html>`_                                                                          ✔                                              ✔                      ✔                       ✔
`myTREZOR <mytrezor.html>`_                          ✔                        ✔                      ✔                                              ✔                      ✔                       ✔                      ✔                      ✔                      ✔
`Sentinel <sentinel.html>`_                                                                                                                                                ✔                       ✔
==================================================== ======================== ====================== ====================== ======================= ====================== ======================= ====================== ====================== ====================== ======================

LEGEND |
:icon:`cog` Basic Setup |
:icon:`life-ring` Safe Recovery |
:icon:`exchange` Personal wallets |
:icon:`users` Shared wallets |
:icon:`user-secret` Hidden Wallets With Passphrase |
:icon:`bars` Multiple Accounts |
:icon:`eye-slash` Watch-only mode |
:icon:`eye` Show on TREZOR |
:icon:`upload` Update Firmware |
:icon:`fire` Wipe device | 

.. :icon:`th` Smart PIN Matrix |

Using TREZOR With Online Services
---------------------------------

.. image:: images/photo01.png

Following websites allow you a secure password-less **Sign in with TREZOR** or other great bitcoin related services, 
e.g. creating invoices from your TREZOR accounts. Click on the name of a service for more details.

==================================================== ===================================== ==============================================================================================
Service                                              Feature(s)                            Description
`Bitex <bitex.html>`_                                :icon:`lock`                          Real time bitcoin exchange.
`Bitwala <bitwala.html>`_                            :icon:`exchange`                      Payment processor. Pay your Euro bills with Bitcoin.
`Cashila <cashila.html>`_                            :icon:`lock` :icon:`exchange`         Payment processor. Pay your Euro bills with Bitcoin.
`Coinmap <coinmap.html>`_                            :icon:`lock` :icon:`umbrella`         Map of bitcoin shops and businesses.
`Coinpayments <coinpayments.html>`_                  :icon:`lock`                          Payment processor service supporting various cryptocurrencies.
`Osclass <osclass.html>`_                            :icon:`lock`                          Open-source platform for easy creation of classifieds sites. 
`Strip4Bit <strip4bit.html>`_                        :icon:`lock` :icon:`umbrella`         Adult site allowing users to sign up privately in a secure way. 
`Telebit <telebit.html>`_                            :icon:`exchange`                      Android wallet coupled to Telegram Messenger
`Wordpress <wordpress.html>`_                        :icon:`lock`                          Blog hosting and publishing platform.
==================================================== ===================================== ==============================================================================================

.. `Drupal CMS <drupal.html>`_                       :icon:`lock`                          Content management platform.
.. `Slush pool <slush-pool.html>`_                   :icon:`lock`, :icon:`umbrella`        The first mining pool ever and inventor of mining concept.
.. `CoinSimple <coinsimple.html>`_                   :icon:`lock`  	                       Bitcoin invoicing service and wallet connector.

LEGEND | 
:icon:`lock` `Sign in with TREZOR <../trezor-tech/api-connect.html>`_ | 
:icon:`umbrella` Sign up with TREZOR | :icon:`exchange` Move funds directly from/to TREZOR

Recovering Funds without TREZOR Device 
--------------------------------------

.. image:: images/photo03.png

In case your TREZOR device gets lost or damaged, you can access your bitcoins fast using your :download:`paper backup <../trezor-user/images/recovery_card.pdf>` and one of the following wallets:
 
- `ArcBit <http://arcbit.io>`_ (iOS)
- `Copay <https://copay.io>`_ (Linux, Windows, OSX, Android, iOS, Windows phone)
- `Electrum <https://electrum.org/#download>`_ (Linux, Windows, OSX, Android), `recovery manual <https://www.buybitcoinworldwide.com/kb/restore-trezor-seed-electrum>`_
- `Encompass <https://maza.club/encompass>`_ (Linux, Windows, Android)
- `MultiBit HD <https://multibit.org>`_ (Linux, Windows, OSX) - only the first account can be accessed, passphrase not supported
- `Mycelium <https://play.google.com/store/apps/details?id=com.mycelium.wallet>`_ (Android), `recovery manual <https://www.buybitcoinworldwide.com/kb/restore-trezor-seed-mycelium-android>`_
- `Wallet32 <https://play.google.com/store/apps/details?id=com.bonsai.wallet32>`_ (Android)
.. - `Mycelium <https://itunes.apple.com/ca/app/mycelium-bitcoin-wallet/id943912290>`_ (iOS), only 12 word recovery is supported

.. Ongoing Integrations
.. --------------------
.. image:: images/photo04.png
.. Are you actively working on adding TREZOR support to your application? Get in touch with us via integration@satoshilabs.com. We will gladly include you in the following list.
.. - `Coinkite <https://coinkite.com>`_ - Standard and multisig wallet planned
.. - `Coyno <https://beta.coyno.com/>`_ - Watch-only wallet service in beta phase
.. - `Drupal CMS <https://www.drupal.org>`_ - Sign in with TREZOR work in progress
.. - `Slush pool <http://mining.bitcoin.cz/home/>`_ - Sign in with TREZOR work in progress
.. - `Bitstock <https://www.bitstock.com>`_ - Sign in with TREZOR planned
.. - `Bitstamp <https://www.bitstamp.net>`_ - Sign in with TREZOR planned

License
-------

The contents of this documentation are licensed under Creative Commons `CC BY-SA 4.0 <https://creativecommons.org/licenses/by-sa/4.0/>`_ license.

Contributing
------------

The project is hosted `on GitHub <https://github.com/satoshilabs/docs>`_ and pull requests are welcome!

.. toctree::
   :hidden:
   :maxdepth: 1
   
   arcbit
   bitex
   bitwala
   extension
   cashila
   coinmap
   coinpayments 
   coinprism 
   copay
   electrum 
   electrum-dash
   electrum-ltc
   encompass 
   greenaddress
   multibit 
   mycelium 
   mytrezor
   osclass
   sentinel
   strip4bit
   telebit
   wordpress
  
   
