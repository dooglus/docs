Setting up Chrome extension on Linux
====================================

`Chrome extension <https://chrome.google.com/webstore/detail/jcjjhjgimijdkoamemaghajlhegmoclj>`_ is an convenient way of using TREZOR without a need of installing proprietary software on your computer.
However, on Linux, users need to perform additional configuration of their system.

After you install Chrome extension in |mytrezor| on Linux, you will be asked to install additional package (DEB or RPM), which configures UDEV rules of your system.
Those additional UDEV rules are necessary for communication between the device and Chrome browser.

Manual configuration of UDEV rules
----------------------------------

For rare Linux distributions without DEB or RPM package managers, please follow these steps for adding UDEV rules manually:

1. Disconect your TREZOR device.
2. Create new file `/etc/udev/rules.d/51-trezor.rules` in your favourite text editor (root privileges are necessary).
3. Copy the following two lines, paste them into the file and save it.

::

  SUBSYSTEM=="usb", ATTR{idVendor}=="534c", ATTR{idProduct}=="0001", MODE="0666", GROUP="dialout", SYMLINK+="trezor%n"
  KERNEL=="hidraw*", ATTRS{idVendor}=="534c", ATTRS{idProduct}=="0001",  MODE="0666", GROUP="dialout"

4. Go to |mytrezor| and connect your TREZOR.

.. |myTrezor| raw:: html

   <a href="http://mytrezor.com" target="_blank">myTREZOR.com</a>
