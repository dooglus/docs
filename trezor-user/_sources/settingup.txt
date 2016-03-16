Setting up your TREZOR device
=============================

The TREZOR works with almost any computer that has a USB port and an internet connection.  To allow |myTrezor| wallet to communicate with the TREZOR you need to install a piece of software called the TREZOR bridge.  If you go to the |myTrezor| website you should see a page with a Download link.  Download the TREZOR bridge and follow the instructions on the screen.

.. note:: We also provide `Chrome extension <https://chrome.google.com/webstore/detail/jcjjhjgimijdkoamemaghajlhegmoclj>`_, which works on all platforms. However, Linux users need to perform additional configuration of their system, please see :doc:`Setting up Chrome extension on Linux <settingupchromeonlinux>`.

Once you've got the TREZOR bridge installed go to |myTrezor| again.  This time you should see a web page welcoming you and asking for a device label:

.. image:: images/welcometosetup.png

Enter a new name for your TREZOR device and press Continue.  You should see the first seed word.  Now go on to :doc:`Filling out your Recovery Card <fillingoutyourrecoverycard>`.

.. note:: There are also several :doc:`Advanced settings <advanced_settings>` that you can configure.

.. toctree::
   :maxdepth: 2

   settingupchromeonlinux
   fillingoutyourrecoverycard
   basic_settings
   enteringyourpin


.. You don't need to use the |myTrezor| webservice if you want to use your TREZOR device.  You can use any bitcoin software that supports TREZOR including:

 - Electrum
 - Multibit

.. |myTrezor| raw:: html

   <a href="http://mytrezor.com" target="_blank">myTREZOR.com</a>
