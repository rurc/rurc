rurc integration/staging tree
================================

http://rurc.com/

Copyright (c) 2009-2013 Bitcoin Developers
Copyright (c) 2014 Vertcoin Developers
Copyright (c) 2015 rurc Developers

What is rurc?
----------------

rurc is rock solid, rare cryptocoin bar using Lyra2RE as a proof-of-work algorithm.

 - 2.5 minute block targets
 - 1971000 total RURC
 - 5 coins per block
 - Block reward will half at blocks 210240, 420480, 630720 (one year between each)
 - Last PoW block is 840960
 - Difficulty retargeting with Kimoto's Gravity Well
 - Stealth addresses (experimental, use at own risk)


Ports for client connectivity
-----------------------------
 
Mainnet RPC 7047
Mainnet P2P 7046

Testnet RPC 17047
Testnet P2P 17046

License
-------

rurc is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Will be developed further.

Compiling
---------

Dependencies needed are exactly same as in Vertcoin;

	sudo apt-get install automake autoconf libtool build-essential libgmp-dev

Also, we need to install the secp256k1 module:
	
	cd /opt
	git clone https://github.com/bitcoin/secp256k1
	cd secp256k1
	sudo ./autogen.sh
	sudo ./configure
	sudo make
	sudo make install (optional)

Update LD cache so the system knows about the freshly installed secp256k1 existence,

	sudo ld-config

Makefiles for the core code are in `src/`. To compile and run them, type in rurc directory:

    cd src
	./autogen.sh (if building from git repository)
	./configure
	make -f makefile.unix
	strip rurcd
	
To run freshly compiled daemon, type:
	
	./rurcd

Makefiles for the Qt client are in `src/`. To compile and run them:

	cd src
	./autogen.sh (if building from git repository)
	./configure
    make -f makefile.linux-mingw
	strip rurc-qt
	
To run freshly compiled Qt client, type:
	
    ./rurc-qt

