## Contents
1. [Delegates](#delegates)
  1. [What is this delegate system?](#dWhat)
  2. [How do I become a delegate?](#dHow)
  3. [What's an active or standby delegate?](#standbyActive)
2. [Forging](#forging)
  1. [What is forging?](#fWhat)
  2. [What are the system requirements to forge?](#fSystemReq)
  3. [How do I forge?](#fHow)
  4. [How is the block forger picked?](#hForger)
  5. [How much can I forge?](#fMuch)

## <a name="delegates"></a>Delegates

### <a name="dWhat"></a>What is this delegate system?
Lisk uses the Delegated Proof of Stake (DPoS) consensus algorithms.  The network is secured and/or protected by 101 active delegates.  Each delegate is elected by the stakeholders of LSK.  Once voted into the list of active delegates they are given the authority to generate blocks.  Every Lisk stakeholder can be a part of the electoral process, by placing votes for delegates in their favour, or by becoming a candidate themselves.
The duty of the 101 active delegates is to secure the Lisk main blockchain (sidechains have their own delegates). In order to provide an incentive to secure the network, transaction fees on the network are distributed equally amongst the 101 active delegates. In addition, an inflationary block reward (aka forging reward) is distributed to each block generator.

### <a name="dHow"></a>How do I become a delegate?
To become a delegate you first need to register a delegate username within the client. After the registration your account ID appears in the list of all delegates. The registration fee is currently 25 LSK. After that you will have to setup your own Lisk server and set it to your delegate. Here are some handy guides to get you started.
<br />
<ul>
<li><a href="https://forum.lisk.io/viewtopic.php?t=1119">Becoming a Lisk Delegate and Forging Activation - by densmirnov</a></li>
<li><a href="https://forum.lisk.io/viewtopic.php?f=38&t=408">Secure basic setup of a Delegate server - by CC001</a></li>
</ul>



### <a name="standbyActive"></a>What's an active or standby delegate?
Every delegate is placed at a specific position on the delegate ranking list. The number of votes determines that position. All delegates with a rank between 1 and 101 are active delegates. All other delegates with a rank over 101 (102-∞) are classified as standby delegates.  Only the 101 active delegates will actually forge and earn rewards.  The standby delegates are there only to replace an active delegate if they lose enough votes to get bumped out.

## <a name="forging"></a>Forging

### <a name="fWhat"></a>What is forging?
Forging is another word for block generation, at Bitcoin this process is called mining.  Lisk utilizes an inflationary forging rewards system which creates new LSK for every successful block.  More information about this below.

### <a name="fSystemReq"></a>What are the system requirements to forge?
The most important factor is your internet connection latency. Exact numbers will be revealed in the future. Right now we estimate that any cloud hosting provider should be more than sufficient.

Other important factors are memory and CPU count.  We currently recommend at least 2GB memory and a dual core processor as an active delegate.

### <a name="fHow"></a>How do I forge?
Once you have a delegate and it is voted into the top 101, you would just need to enable forging on a node that is always running.  There are two methods to enable forging:
* You can login to the client user interface and enable forging by hand. The problem with this method is, that if your client restarts (due to an error or server update) forging will need to be enabled again.
* For optimum productivity, it is recommended to run your own node and insert your passphrase into the config.json file. Best to do this before you become an active delegate. Upon starting the Lisk client, forging will be automatically enabled for all accounts for which passphrases are specified in the config.json. Which means after restarting your client, forging will continue without interruption.
You should also be running the newest version of Lisk on the node you have forging enabled.

## <a name="hForger"></a>How is the block forger picked?
Lisk DPoS functions through a series of rounds. Rounds consist of 101 individual blocks. Each of the 101 active delegates are randomly assigned 1 block within the round to forge. If a selected delegate is unable to forge their assigned block, activity from that block moves to the next block in the round.

### <a name="fMuch"></a>How much can I forge?
Delegates earn an equal share of all regular transaction fees occurring on the network.  The total share of regular transaction fees, is dependent on the volume of transactions occurring on the network for a given round.

In addition to those fees, delegates get forging rewards.  The forging rewards occur at a fixed rate per block, and change over the course of the network’s lifetime as follows:
* 5 LSK per block - in the 1st year.
* 4 LSK per block - in the 2nd year.
* 3 LSK per block - in the 3rd year.
* 2 LSK per block - in the 4th year.
* 1 LSK per block – in all other years.
