### Address
An address is a hashed version of a public key. They are very convenient for recieving coins  .. Ex. 9569486828221897676L

### Bapp (Dapp, Blockchain App, App)
A decentralized application, which is running in a sidechain of Lisk. If you add a bapp to Lisk, an entry will be made on the blockchain. This will "register" it and makes it visible to everyone.

### Bapp Store
A universal and decentralized store which lists ALL dapps on the network. (Doesn't matter if working, not working, offline, online, not complete or completely finished).

### BIP39
Is the implementation of a mnemonic code or mnemonic sentence (a group of easy to remember words) for generating deterministic keys.  Lisk integrates mnemonic checksumming of passphrases to make sure it conforms to the BIP39 standard and that passphrase is used to generate your account.

### Block
A block is a group of transactions that were submitted to the network since the last block.  Each block (except for genesis block) references one previous block to form the tree called the blockchain.

### Block Height
Is the sequential number on the blockchain of a block. Height 0 refers to the genesis block.  Current block height refers to the number of the most recent valid block.

### Blockchain
A public ledger of all confirmed transactions in a form of a tree of all valid blocks. Unconfirmed transactions are not part of the blockchain. If a node disagrees on which blocks are valid, a fork happens.

### Brain wallet
Instead of storing keys in a wallet file, security works via a secret passphrase.  Wallets are decentralized and kept on the network.  When you create an account, your secret passphrase is used to generate your account on the blockchain.  Once your account is generated, you can unlock it and access it by using your passphrase.  Lisk uses a brain wallet.

### Delegate
A Lisk account which simply registered to be a delegate on the network (making it a special type of account).

### DPoS
This is short for Delegates Proof of Stake.  It is the algorithm Lisk uses to secure the network.  It differentiates  from regular PoS (Proof of Stake) as only the top 101 delegates (determined by voting weight of voters) are actively forging and securing the network.

### Fork
When a node does not agree on a block, a fork happens and that node create a separate blockchain from the one it disagrees with.

### Full client
A client which stays in sync with the mainchain and maintains a full copy of the blockchain.  This is also a node or peer on the network.

### Genesis Block
The very first block in the blockchain with hard-coded contents. The Genesis block was released on May 24, 2016 at 8pm UTC.

### Hard Fork
Typically referred to as a block when all clients must be updated to a certain version.  Clients that are not updated, fork onto a different chain then the ones that are updated because of a change in the core code.

### Lite client
A client which connects to a full client on the network and does NOT maintain a copy of the blockchain. It can instantly launch without syncing.

### LSK
The currency code for Lisk.

### Node (Peer)
A server/computer/etc. that has installed the Lisk full client and is connected to the internet.

### Public Key
A cryptographic key that can be obtained and used by anyone to encrypt messages intended for a particular recipient, such that the encrypted messages can be deciphered only by using a second key that is known only to the recipient.

### Sidechain
A custom blockchain, which is a fully autonomous blockchain secured by its own nodes. Every bapp is one new sidechain.

### Standby delegates
All delegate accounts from rank 102 until infinity. These accounts do not actively forge and are only waiting for an opportunity to be in the top 101.

### Top (active) delegates
The Lisk accounts who are configured on a node to actively secure the mainchain. Only 101 with the most vote weight.

### Transaction Fee
The amount that an account pays to have a transaction be included in a block. 
