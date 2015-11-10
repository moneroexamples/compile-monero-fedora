# Compile Monero on Fedora 23 x86_64
The example shows how to compile current github version of [Monero](https://getmonero.org/), as of 10 Nov 2015,
on Fedora 23 x86_64.

## Preparation
Before proceeding to the compilation, the following packages are required:

```bash
#install git
sudo dnf install git

# install dependencies
sudo dnf install make automake cmake gcc-c++ boost-devel miniupnpc-devel graphviz doxygen unbound-devel libdb-devel
```

## Compilation
Having the dependencies, we can download the current Monero version and compile it as follows:

```bash
# download the latest bitmonero source code from github
git clone https://github.com/monero-project/bitmonero.git

# go into bitmonero folder
cd bitmonero/

# compile
# cmake . #  optional for configuration and checking what is available or missing
make # or make -j number_of_threads, e.g., make -j 2
```
## Installation (optional)
After successful compilation, the Monero binaries should be located in `./bin`

I usually move the binaries into `/opt/bitmonero/` folder. This can be done
as follows:

```bash
# optional
sudo mkdir /opt/bitmonero
sudo mv ./build/release/bin/* /opt/bitmonero/
```

Now we can start the Monero daemon and let it
download the blockchain and synchronize itself with the Monero network. After that, you can run your the `simplewallet`.

```bash
# launch the Monero daemon and let it synchronize with the Monero network
/opt/bitmonero/bitmonerod

# launch the Monero wallet
/opt/bitmonero/simplewallet
```


## How can you help?

Constructive criticism, code and website edits are always good. They can be made through github.

Some Monero are also welcome:
```
48daf1rG3hE1Txapcsxh6WXNe9MLNKtu7W7tKTivtSoVLHErYzvdcpea2nSTgGkz66RFP4GKVAsTV14v6G3oddBTHfxP6tU
```
