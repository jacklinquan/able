Android Bluetooth Low Energy
============================

`Python <https://github.com/kivy/python-for-android>`_ interface to Android Bluetooth Low Energy API.

Generated documentation: http://able.readthedocs.org

Changes to the API:

1: on_device(device, rssi, raw_ad)

device event handler. Event is dispatched when device is found during a scan.

Parameters:	

device – BluetoothDevice Java object

rssi – the RSSI value for the remote device

raw_ad – raw advertisement bytearray

2: new method added

enable_indications(characteristic)

"enabling indication" is needed for some device like micro:bit to use ble uart read function.


Build
-----

The following instructions are for building app with `buildozer <https://github.com/kivy/buildozer/>`_ tool.

Download the `able` recipes directory: https://github.com/b3b/able/tree/master/recipes .

Path to recipes directory should be set in buildozer.spec::

   p4a.local_recipes = /path/to/downloaded/recipes


`able` recipe should be added to buildozer.spec requirements::

   requirements = hostpython2,kivy,android,able


Bluetooth permissions should be requested in buildozer.spec::

    android.permissions = BLUETOOTH, BLUETOOTH_ADMIN, ACCESS_COARSE_LOCATION


App configuration example: `buildozer.spec <https://github.com/b3b/able/tree/master/examples/alert/buildozer.spec>`_
