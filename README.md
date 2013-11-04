stratum-mining-proxy
====================

Application providing HTTP/getwork protocol <--> Stratum ,Stratum/LTC, Stratum/Qrk mining protocols bridge

Installation using Github for Linux Debian
------------------------------------------
This is advanced option for experienced users, but give you the easiest way for updating the proxy.

1. git clone https://github.com/gritche70/Stratum-mining-proxy-quark.git
2. cd stratum-mining-proxy-quark
3. sudo apt-get install python-dev # Development package of Python are necessary
4. sudo python distribute_setup.py # This will upgrade setuptools package
5. cd litecoin_scrypt
   python setup.py install # Build and install LTC scrypt extension
   cd ..
6. cd quarkcoin-hash-python
   python setup.py install # Build and install Quark scrypt extention	
   cd ..
7. python setup.py develop # This will install required dependencies (namely Twisted and Stratum libraries), but don't install the package into the system.
7. You can start the Stratum proxy by typing "./mining_proxy.py" in the terminal window. Using default settings, it connects to Itzod's mining pool.
   Also you have ability to start Stratum/LTC proxy by typing  "./mining-proxy.py -pa scrypt". Using default settings, it connects to LTCMine mining pool.
8. If you want to connect to another pool or change other proxy settings, type "./mining_proxy.py --help".
9. If you want to update the proxy, type "git pull" in the package directory.

Compiling midstate C extension
------------------------------
For some really big operations using getwork interface of this proxy, you'll find
useful "midstatec" C extension, which significantly speeds up midstate calculations
(yes, plain python implementation is *so* slow). For enabling this extension,
just type "make" in midstatec directory. Proxy will auto-detect compiled extension
on next startup.

Contact
-------

pj(at)viveleboulot.fr
