## Contents
1. [What is Lisk?](#wLisk)
2. [What is DPoS?](#wDPoS)
3. [What is Forging?](#wForging)
4. [How do I forge?](#hForge)
5. [How is the block forger picked?](#hForger)
6. [How is Lisk different from Crypti?](#LiskCrypti)
7. [What is this mainnet and testnet?](#mainTest)


## <a name="wLisk"></a>What is Lisk?
Lisk is a public blockchain platform and framework to develop decentralized, blockchain-based applications in JavaScript. It was forked from Crypti by Max Kordek and Olivier Beddows in early 2016.  Developers may build blockchain applications which utilize their own sidechain interlinked to the Lisk platform. Thanks to the scalability and flexibility of sidechains developers can implement and customize their blockchain applications entirely. Lisk is a non-profit organization, founded in 2016 by Max Kordek and Oliver Beddows.

## <a name="wDPoS"></a>What is DPoS?
Lisk uses the DPoS (Delegates Proof of Stake) algorithm originally created by BitShares. What differentiates it from regular PoS (Proof of Stake) is that only the top 101 delegates (determined by voting weight of voters) are actively forging and securing the network.

## <a name="wForging"></a>What is Forging?
Lisk utilizes an inflationary forging rewards system which creates new LSK for every successful block. During year 1, the forging rewards are set at 5 LSK per block. Every 3,000,000 blocks (~1 year) forging rewards are reduced by 1 LSK, ending at 1 LSK per block after 5 years. The forging rewards will then stay at 1 LSK per block indefinitely. The Forging Rewards will be equally distributed through all active (top 101) delegates, same as any network fees.

## <a name="hForge"></a>How do I forge?
To forge, three criteria have to met:

1. You have to register a delegate with your account.
2. You have to acquire enough voting weight to be in the top 101 delegates.
3. You have to have your account enable forging on a Lisk node.

## <a name="hForger"></a>How is forger picked?
Lisk DPoS functions through a series of rounds. Rounds consist of 101 individual blocks. Each of the 101 active delegates are randomly assigned 1 block within the round to forge. If a selected delegate is unable to forge their assigned block, activity from that block moves to the next block in the round.

## <a name="LiskCrypti"></a>How is Lisk different from Crypti?
Lisk is a fork of Crypti, so it started out just as Crypti.  Since then though, the code is completely different.  Some of the notable differences are:

* The database has been changed from SQLite to PostgreSQL.
* Completely open source and the whole development procedure is happening in public on GitHub.
* BIP39 enforced for all passphrases
* Lots of optimizations to peer code
* Development is continuing and active, while Crypti seems to have stopped.

## <a name="mainTest"></a>What is this mainnet and testnet?
The mainnet is the actual network that Lisk resides on.  All the coin, blocks, and transactions there are real.  The testnet is a Lisk network where the coins have no value.  This network is used for testing by anyone and is a free area to explore Lisk.