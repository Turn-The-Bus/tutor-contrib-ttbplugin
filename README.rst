ttbplugin plugin for `Tutor <https://docs.tutor.edly.io>`__
###########################################################

ttbplugin plugin for Tutor. This is used to initialize the Google Firebase credentials in the Open edX platform.
The actual credentials are stored in Github secrets and are injected into the Open edX platform during the deploy process.


Installation
************

.. code-block:: bash

    pip install git+https://github.com/Turn-The-Bus/tutor-contrib-ttbplugin

Usage
*****

.. code-block:: bash

    tutor plugins enable ttbplugin


License
*******

This software is licensed under the terms of the AGPLv3.
