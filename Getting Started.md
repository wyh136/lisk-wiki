## Contents
1. [Downloads](#downloads)
  1. [Pre-requisite for Installation](#requisite)
  2. [Lisk Client (Full Node)](#client)
    1. [Binary Installation](#binary)
    2. [Docker Installation](#docker)
  3. [Lisk Nano](#nano)
2. [Obtaining Lisk](#obtaining)
  1. [Buy Bitcoin (Coinbase, Kraken, others)](#buy)
  2. [Exchange BTC for LSK](#exchange)
  3. [Forging Rewards/Become a Delegate](#forging)

## <a name="downloads"></a>Downloads

### <a name="requisite"></a>Pre-requisite for Installation
You will need some basic Linux knowledge to use the Binary Installation.  If you have never used linux before, you can try the Docker version or the Nano client (highly recommended).

### <a name="client"></a>Lisk Client (Full Node)

#### <a name="binary"></a>Binary Installation
The following operating systems and architectures are supported:
* Linux (x86_64)
* Linux (i686)
* Linux (armv6l)
* Linux (armv7l)
* Darwin (x86_64)
* FreeBSD (amd64)

#### <a name="docker"></a>Docker Installation
**It is recommended you first become familiar with Docker if you are not already**

To install the latest version of Lisk as a docker container, please proceed with the following:

Download the appropriate docker image:

Mainnet:
```
docker pull lisk/mainnet
```
Testnet:
```
docker pull lisk/testnet
```
Install the docker image (executed only once per installation):

Mainnet:
```
docker run -d --restart=always -p 0.0.0.0:8000:8000 lisk/mainnet
```
Testnet:
```
docker run -d --restart=always -p 0.0.0.0:7000:7000 lisk/testnet
```
*NOTE: On Windows or Mac OS X, these commands are issued from within the Docker Quickstart Terminal.*

Upon successful completion, you will have a running Lisk node with an up-to-date snapshot of the blockchain. The container is configured to automatically restart upon reboot of the server or any occurrence of an error.

To access the Lisk web client, open: http://{IP of docker container}:8000/ if on the mainnet or http://{IP of docker container}:7000/ if on a testnet.

### <a name="nano"></a>Lisk Nano

Lisk Nano enables you to send and receive transactions on the Lisk network and provides our users with an easy accessible minimal feature-set. It connects to other nodes on the Lisk network, therefore there is no need for blockchain syncing.

* [Windows](https://downloads.lisk.io/lisk-nano/0.1.1/lisk-nano-0.1.1.exe)
* [macOS](https://downloads.lisk.io/lisk-nano/0.1.1/lisk-nano-0.1.1.dmg)
* [Linux](https://downloads.lisk.io/lisk-nano/0.1.1/lisk-nano-0.1.1.deb)

## <a name="obtaining"></a>Obtaining Lisk

### <a name="buy"></a>Buy Bitcoin
First, you will need to buy some Bitcoin that you can exchange for Lisk.  Two of the most popular sites to easily/quickly get bitcoin are:
* [Coinbase](https://www.coinbase.com/) (USD, EUR, UK, CAD, Australian, Singapore)
* [Kraken](https://www.kraken.com) (USD, EUR, GBP, JPY, CAD)

### <a name="exchange"></a>Exchange BTC for LSK
Once you have some Bitcoin, you can transfer that to any exchange that currently trades LSK/BTC and obtain some Lisk.  Some of these exchanges include:
* BitBay
* BitMEX
* Bittrex
* BloomBit
* Chameleon Bit
* HitBTC
* Livecoin
* Poloniex
* YoBit

### <a name="forging"></a>Forging Rewards/Become a Delegate
Lisk utilizes DPoS (Delegates Proof of Stake) with an inflationary forging rewards system which creates new LSK for every successful block.  The forging rewards are equally distributed through all active delegates, same as any network fees.  To become an active delegate you have to be voted on by Lisk accounts.  A delegate's approval is determined by the total Lisk held in accounts that have voted for them.  The top 101 delegates with the most approval, are the active delegates that receive rewards & fees.