LongCoin integration/staging tree
================================

http://www.longcoin.org

Copyright (c) 2009-2013 Bitcoin Developers
Copyright (c) 2013-2014 LongCoin Developers

What is LongCoin?
----------------

LongCoin is a lite version of Bitcoin using X11 as a proof-of-work algorithm.
 - Super secure hashing algorithm: 11 rounds of scientific hashing functions (blake, bmw, groestl, jh, keccak, skein, luffa, cubehash, shavite, simd, echo)
 - Block rewards:	Block 0 - 0 : 0 LNG
					Block 1 - 1 : 100,000 LNG (presale, promotion)
					Blocks 2 - 360 : 0 LNG (6 hours)
					Blocks 361 - 43200 : 0.5 LNG (1 month)
					Blocks 43201 - 525600 : 0.25 LNG (1 year)
					Blocks 525601 - 2628000 : 0.125 LNG (5 years)
					Blocks 2628001 - 24763840: 0.0625 LNG (47 years)
 - GPU/CPU only mining
 - Block generation: 1 minute
 - Difficulty Retargets every block using Long Gravity Wave
 - 2M Coins PoW
 - Anonymous blockchain using LongSend technology (Based on CoinJoin): Beta Testing

For more information, as well as an immediately useable, binary version of
the LongCoin client sofware, see http://www.longcoin.org.

License
-------

LongCoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the LongCoin
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion (if they haven't already) on the
[mailing list](http://sourceforge.net/mailarchive/forum.php?forum_name=bitcoin-development).

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.txt`) or are
controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/longcoinproject/longcoin/tags) are created
regularly to indicate new official, stable release versions of LongCoin.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test. Please be patient and help out, and
remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write unit tests for new code, and to
submit new unit tests for old code.

Unit tests for the core code are in `src/test/`. To compile and run them:

    cd src; make -f makefile.unix test

Unit tests for the GUI code are in `src/qt/test/`. To compile and run them:

    qmake BITCOIN_QT_TEST=1 -o Makefile.test bitcoin-qt.pro
    make -f Makefile.test
    ./longcoin-qt_test

