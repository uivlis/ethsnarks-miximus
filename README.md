# Miximus

Miximus is a self-service coin mixer and anonymous transfer method for Ethereum, it accepts deposits of 1 ETH, then allows you to withdraw coins by providing a zkSNARK proof that proves you know the spend key for one unspent coin without revealing which one it is.

For more information, see:

 * [Miximus.sol](contracts/Miximus.sol)
 * [miximus.py](python/miximus.py)
 * [test_miximus.py](python/test/test_miximus.py)
 * [miximus.cpp](src/miximus.cpp)

The zkSNARK prover is built as a native library which can plug-in to your application, when provided with the correct arguments it returns the zkSNARK proof as JSON. While you may think of zkSNARKs as being slow - the algorithms chosen for Miximus mean proofs can be made in 5 seconds, however we're still studying their security properties.

## Building

Type `make` - the first time you run it will retrieve submodules, setup cmake and build everything, for more information about the build process see the [Travis-CI build logs](https://travis-ci.org/HarryR/ethsnarks).

Before building, you may need to retrieve the source code for the dependencies:

	git submodule update --init --recursive

The following dependencies (for Linux) are needed:

 * cmake
 * g++ or clang++
 * gmp
 * libcrypto
 * boost
 * npm / nvm


## Maintainers

[@HarryR](https://github.com/HarryR)
