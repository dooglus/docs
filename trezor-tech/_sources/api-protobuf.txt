Low level API
=============

TREZOR communicates using a simple request-response model.
Messages are exchanged always in a purely synchronous fashion over `USB HID <https://en.wikipedia.org/wiki/USB_HID>`_.
These messages are serialized into binary format using `Protocol Buffers <https://en.wikipedia.org/wiki/Protocol_Buffers>`_.

USB HID
-------

The SatoshiLabs Vendor ID is ``0x534c`` and TREZOR's Device ID ``0x0001``.

If you've never worked with HID devices before, it may be helpful to take a look at the `Java implementation <https://github.com/trezor/trezor-android/blob/master/src/com/satoshilabs/trezor/Trezor.java>`_ which establishes a connection to TREZOR and reads and writes to the device.

Protobuf definitions
--------------------

Protobuf message definitions are stored in the `trezor-common <https://github.com/trezor/trezor-common/tree/master/protob>`_ repository.  The following files are of interest:

- `messages.proto <https://github.com/trezor/trezor-common/blob/master/protob/messages.proto>`_ -- describes messages
- `types.proto <https://github.com/trezor/trezor-common/blob/master/protob/types.proto>`_ -- describes data structures sent within the messages

API workflows
-------------

Message ordering in the TREZOR protobuf protocol is significant.  You will find a list of standard workflows bellow:

.. toctree::
   :maxdepth: 2

   api-workflows