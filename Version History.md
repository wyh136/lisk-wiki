# Contents

## Versions
| [0.5.0](#050)  |      ||||
| ------------- |-------------|-----|-----|-----|
| [0.4.1](#041) | [0.4.0](#040)  |   |   |   |
| [0.3.1](#031) | [0.3.0](#030) |   |   |   |
| [0.2.3](#023) | [0.2.2](#022) | [0.2.1](#021) | [0.2.0](#020) |   |
| [0.1.4](#014) | [0.1.3](#013) | [0.1.2](#012) | [0.1.1](#011) | [0.1.0](#010) |



# <a name="050"></a>0.5.0

* Closed [#104](https://github.com/LiskHQ/lisk/issues/104). Implementing peer sweeper. Collecting peer changes and sweeping in batches.
* Closed [#294](https://github.com/LiskHQ/lisk/issues/294). Loading unconfirmed transactions from "good" peer.
* Closed [#284](https://github.com/LiskHQ/lisk/issues/284). Emitting delegates/fork event after forking.
* Closed [#255](https://github.com/LiskHQ/lisk/issues/255). Matching genesis block with database.
* Closed [#141](https://github.com/LiskHQ/lisk/issues/141). Attempting to load delegates on each cycle.
* Closed [#297](https://github.com/LiskHQ/lisk/issues/297). Improved peers/chain selection reliability thanks to new `broadhash` implementation.
* Closed [#298](https://github.com/LiskHQ/lisk/issues/298). Array items are not unique in Loader.prototype.onPeersReady.
- Closed [#259](https://github.com/LiskHQ/lisk/issues/259). Mitigating against fork cause 2.
 * Restoring sane API behaviour for POST /peer/transactions. 
     * Returning error on already processed transaction.
     * Returning error on already confirmed transaction.
* Fixed [#253](https://github.com/LiskHQ/lisk/issues/253). Adding missing check on transaction.
* Closed [#306](https://github.com/LiskHQ/lisk/issues/306). Implemented new transaction pool and broadcast queuing
 * Adding new API endpoints:
     * GET `/api/transactions/multisignatures/get`
     * GET `/api/transactions/multisignatures`
     * GET `/api/transactions/queued/get`
     * GET `/api/transactions/queued`
* Rewrote and refactored multisignature module.
* Increased default database connection pool size to `95`.
* Merged [#314](https://github.com/LiskHQ/lisk/issues/314). Prevent "TypeError: Cannot read property 'network' of undefined [@TheGoldenEye](https://github.com/TheGoldenEye).
* Closed [#51](https://github.com/LiskHQ/lisk/issues/51). Fixing invalid getGenesis parameter.
* Closed [#244](https://github.com/LiskHQ/lisk/issues/244). Adding minimal client version parameter.
* Closed [#91](https://github.com/LiskHQ/lisk/issues/91). Validating config.json according to schema.
Do not remove peer on `ETIMEOUT`, only ban for 10 minutes.
* Returning `500` status code upon incorrect network / version.
* Correcting ban on peers returning invalid common block request to 10 minutes.
* Fixed incorrect math operator in `__private.checkDelegates`.
* Disabling forced forging for known nethashes.
* Closed [#316](https://github.com/LiskHQ/lisk/issues/316). Logging warning when delegate slot skipped.
* Increased gzip compression level on express middleware.
* Improved broadcast efficiency. Squashing queued broadcasts from many to one per route. Accepting collection or object on `POST /peer/transactions` and `POST /peer/signatures`.
* Implemented bundled transaction processing. Dramatically speeding up response times for POST /peer/transactions.
* Closed [#307](https://github.com/LiskHQ/lisk/issues/307). Implementing auto recovery from forks.
 * Deleting last block on failed chain comparision and poor `broadhash` efficiency.
 * Deleting losing block in case of received fork 1 and 5.
* Merged [#320](https://github.com/LiskHQ/lisk/issues/320). Allowing "+" char in os version check [@4miners](https://github.com/4miners).
* Closed [#307](https://github.com/LiskHQ/lisk/issues/307). Fixing broken backwards round tick.
 * Refactoring code. Adding `__private.sumRound` function.
 * Fixing property typo in Rounds.prototype.backwardTick.
 * Fixing property typo in Rounds.prototype.tick.
 * Fixing broken round changes on backwards tick.
 * Fixing broken missed blocks on backwards tick.
 * Fixing broken Rounds.prototype.directionSwap.
 * Summing round from blocks on forwards direction.
 * Do not flush round on direction swap.
 * Adding missing direction swaps.
     * Before/after Blocks.prototype.deleteLastBlock.
     * Before/after Blocks.prototype.deleteBlocksBefore.
 1. Marking undone blocks in mem_accounts.
Excluding marked accounts from orphaned mem_accounts check.
* Closed [#319](https://github.com/LiskHQ/lisk/issues/319). Fixing broadhash update reliability.
* Closed [#323](https://github.com/LiskHQ/lisk/issues/323). Fixing bad `setInterval` strategy.
* Shortening various peer ban times from 60 to 10 minutes.
* Closes [#322](https://github.com/LiskHQ/lisk/issues/322). Fixing multisignature processing.
 * Fixing incorrect message bus arguments.
 * Resetting u_multimin, u_multilifetime on startup.
 * Removing nested balancesSequence (causing timeouts).
 * Updating ready state after processing signature.
 * Fixing max keysgroup size check. Adding ability to add exceptions for existing transactions [@TheGoldenEye](https://github.com/TheGoldenEye).
 * Fixing erroneous check on account.multisignatures.
 * Determining multisignatures from sender or transaction asset.
 * Pushing senderPublicKey onto multisignatures.
 * Improving check on requester public key.
 * Improving error messages.


### Frontend

* Using jit-grunt to slightly speed up grunt [@Alevale](https://github.com/Alevale).
* Updating lisk-js dependency.

###Build

* Added PostgreSQL 9.6.x support to `installLisk.sh`.
* Added logrotation support for linux in `installLisk.sh`.
* Implemented `updateConfig.js` for automated config.json updates.
* Improved `installLisk.sh` installation efficiency.
* Add rebuild/url support to `installLisk.sh` for upgrade and install functions.




# <a name="041"></a>0.4.1
### Backend
* Do not apply or undo transaction when syncing (before processing).
* Fixed [#293](https://github.com/LiskHQ/lisk/issues/293). Expected type string but found type null [@Isabello](https://github.com/Isabello).
* Closed [#285](https://github.com/LiskHQ/lisk/issues/285). Moved TOP=true param to config.json [@Isabello](https://github.com/Isabello).
* Fixed state filter on ```GET /api/peers``` endpoint.
* Using extend consistently for all object extension.
* Handling NaN port in Peers.prototype.inspect.
* Revised and improved schema validations.


###Frontend
* Merged [#79](https://github.com/LiskHQ/lisk-ui/pull/79). Fixing cramped high page numbers on blockchain page [@slaweet](https://github.com/slaweet).


###Build
* Merged [#49](https://github.com/LiskHQ/lisk-build/pull/49). Updating md5 command for macOS [@Doweig](https://github.com/Doweig).
* Improving block height check in ```lisk.sh``` to show “Unavailable” when query is empty [@Isabello](https://github.com/Isabello).



# <a name="040"></a>0.4.0
### Backend — Accounts
* Closed [#197](https://github.com/LiskHQ/lisk/issues/197). Improving error messages when account does not have enough funds. Yielding sender address and account balance.
* Closed [#266](https://github.com/LiskHQ/lisk/issues/266). Changed behavior of ```POST /api/accounts/open``` and ```POST /api/accounts/generatePublicKey```. New accounts are no longer written to ```mem_accounts```. Added one-time migration to delete dormant accounts which have never received or sent funds.
* Closed [#266](https://github.com/LiskHQ/lisk/issues/266). Verifying public key type, length and format in ```Account.prototype.set``` and ```Account.prototype.merge```.
* Closed [#266](https://github.com/LiskHQ/lisk/issues/266). Added virgin column to mem_accounts. Indicating whether an unconfirmed transaction sent from an account has been applied.
* Closed [#266](https://github.com/LiskHQ/lisk/issues/266). Added ```protect_mem_account``` database trigger. Making ```address```, ```u_username```, ```username```, ```virgin```, ```publicKey``` and ```secondPublicKey``` columns immutable once written.
* Closed [#266](https://github.com/LiskHQ/lisk/issues/266). Added ```senderPublicKey``` exceptions to ```Transaction.prototype.verify```.
* Added missing address validation to ```GET /accounts?address=```.
* Fixed error on ```GET /api/delegates?orderBy=unknown:asc```.
* Fixed error on ```GET /api/delegates?limit=0```.

### Backend — Blocks
* Closed [#163](https://github.com/LiskHQ/lisk/issues/163). Adding default orderBy to ```/api/blocks``` (height:desc).
* Merged [#210](https://github.com/LiskHQ/lisk/pull/210). Block processing rewrite [@fix](https://github.com/fix).
* Preventing data corruption of memory tables after reload or shutdown [#213](https://github.com/LiskHQ/lisk/issues/213).
* Closed [#222](https://github.com/LiskHQ/lisk/issues/222). Fixing block reward calculation within first few blocks after milestone.
* Closed [#258](https://github.com/LiskHQ/lisk/issues/258). Detecting numericality of snapshot round. Allowing ```node app.js —snapshot=foobar``` to default to the highest round.
* Closed [#260](https://github.com/LiskHQ/lisk/issues/260). Removing infinite recursion in ```Loader.prototype.getNetwork```.
* Closed [#276](https://github.com/LiskHQ/lisk/issues/276). Finishing snapshot within ```__private.applyBlock```.
* Closed [#289](https://github.com/LiskHQ/lisk/issues/289). Prevent sync slowdown after receiving unconfirmed transactions.
* Conditionally loading blocks from network; when there has been no block “receipts” over network transport, or when last receipt was over 120 seconds ago.
* Added ```GET /api/loader/status/ping``` endpoint [@34ro](https://github.com/34ro).
* Added ```GET /api/blocks/getEpoch``` endpoint.
* Added ```nethash``` and ```epoch``` properties to ```GET /api/blocks/getStatus```.
* Fixed orphan account check. Excluding ```mem_accounts``` with NULL ```blockId```.
* Fixed invalid type comparison on unapplied rounds.
* Fixed reported block height when rebuilding blockchain.
* Improved error logging with JSON dump of affected block.

### Backend — Transactions
* Closed [#265](https://github.com/LiskHQ/lisk/issues/265). Fixing “Account not found” error when sending transactions to virgin account using ```POST /api/transactions```.
* Fixed [#279](https://github.com/LiskHQ/lisk/issues/279). Removing erroneous unconfirmed transactions.
* Fixed [#279](https://github.com/LiskHQ/lisk/issues/279). Removing redundant double spend collection.
* Fixed undefined is not a function error. After error thrown while verifying transaction bytes.
* Added verification of transaction assets for all transaction types.
* Improved error logging with JSON dump of affected transaction.
* Improved logging of apply / undo of transactions at debug level.
* Performing sender balance checks using bignum arithmetic.

### Backend — Applications
* Closed [#269](https://github.com/LiskHQ/lisk/issues/269). Fixed crash on 404 error for ```POST /api/dapps/install```.
* Downgraded ```npm``` to latest LTS release ```2.15.10```.

### Backend — Peers
* Improving peers db efficiency [#104](https://github.com/LiskHQ/lisk/issues/104). Sequencing peers updates.
* Improving peers db efficiency [#104](https://github.com/LiskHQ/lisk/issues/104). Replacing insert / update with single upsert.
* Improving peers db efficiency [#104](https://github.com/LiskHQ/lisk/issues/104). Chaining database queries when adding dapp peer.
* Closed [#147](https://github.com/LiskHQ/lisk/issues/147). Replacing request with popsicle. Fixing memory leak on large request bodies, e.g. loading blocks from peer.
* Merged [#227](https://github.com/LiskHQ/lisk/pull/227). Improved peer discovery using histogram cut selection of “good” peers [@fix](https://github.com/fix).
* Closed [#231](https://github.com/LiskHQ/lisk/issues/231). Implementing API rate limiter. Individually configurable for both ```/api``` and ```/peer```. Disabled by default.
* Added ```EHEADERS```, ```ERESPONSE```, ```ENETHASH``` peer error codes, extending: https://github.com/blakeembrey/popsicle#error-handling.
* Fixed timers in ```Loader.prototype.onPeerReady```.
* Only trigger ```nextLoadBlock``` if loaded and not already syncing.
* Fixed halt to ```nextLoadUnconfirmedTransactions``` recursion when syncing.
* Fixed halt to ```nextLoadSignatures``` recursion when syncing.
* Checking ```nethash``` for all transport /peer requests.
* Returning JSON response for ```POST /peer/blocks```.
* Returning ```success``` or ```error``` for ```GET /api/peers/get```.
* Added success property to ```GET /peer/transactions```.
* Ignoring already processed or confirmed transactions for ```POST /peer/transactions```.
* Added ```transactionId``` property to ```POST /peer/transactions```.
* Added ```success``` property to ```GET /peer/height```.
* Removing peers which return bad response code.
* Removing peers with invalid request headers.
* Removing peers with invalid nethash.
* Improved logging of peer changes at debug level.
* Increased default peer timeout to 5000 ms.
* Fixed unwanted rejection of seed peers due to lack of ```os```, ```version``` metadata.
* Removed unnecessary peer loopback detection.
* Validating peer headers using zschema only.

### Backend — Refactoring
* Closed [#147](https://github.com/LiskHQ/lisk/issues/147). Dramatically improved CPU and memory efficiency.
* Moved schema validations into separate modules, to eliminate unnecessary continous object creation.
* Added unique ids to schema validations, to better utilize z-schema schema caching.
* Nullifying any large objects identified by memory profiling at the earliest opportunity.
* Decoupled transaction types from modules into separately addressed modules.
* Defining functions on constructor prototype where possible.
* Using ```async``` for control flow, to remove deep nesting of code.
* Fully linted code base using ```jshint``` to a strict standard.
* Created database indexes on memory tables.

### Backend — Tests
* Complete rewrite and abstraction of API tests, for cleaner tests.
* Massively expanded API test coverage, resulting in many fixes.
* Added initial unit test coverage, e.g. for block rewards.

### Backend — Configuration
* Removed unimplemented ```serveHttpAPI/Wallet``` options from ```config.json```.
* Added ```maxUpdatePeers``` option to ```config.json```.
* Added ```trustProxy``` setting to ```config.json```.

### Backend — Dependencies
* Updated all dependencies to latest compatible versions.
* Replaced ```underscore```, ```util-extend``` with ```lodash```.

### Frontend
* Added Polish language support.
* Fixating and updating dependency versions.
* Fixing calls to ```null``` ```u_multisignatures/multisignatures```.
* Fixing call to ```undefined``` ```resp.data.account```.

### Build
* Closed [#44](https://github.com/LiskHQ/lisk/issues/44). Added timestamp to postgresql logs.
* Added empty blockchain.db.gz to allow for starting the blockchain from 0.
* Updating node/lisk-node to 0.12.16.

### Lisk.sh
* Implemented url flag for ```lisk.sh``` to allow remote snapshots to be used with rebuild.
* Updated rebuild logic to allow for local backups to be reused and to specify file name.
* Improved lisk startup to display current block height after start or status is issued.
* Implemented new logic for interactive snapshotting.
* Added progress bar when downloading snapshots.

### Lisk_snapshot.sh
* Implemented ```lisk_snapshot.sh``` for automated database backups.
* Added ```snapshot.json``` for configuring ```lisk_snapshot.sh``` backups.

### installLisk.sh
* Removed duplicated block height check already present in ```lisk.sh```.
* Changed coldstart to use empty blockchain.db.gz.

### Documentation
* Updated upgrade instructions to use automated upgrade.
* Updated testnet installation instructions.

# <a name="031"></a>0.3.1

### Frontend
* Fixed Lisk address validations.

### Backend
* Fixed Lisk address validations.
* Fixing ```/apt/blocks/get?id=``` endpoint.
* Improved peers connectivity / preventing network partitioning.
* Improved logging when rebuilding chain.
* Set default loadPerIteration to 1000.
* Temporary extension of reward offset.
* Reverted forging timeout feature which was causing network to pause.

# <a name="030"></a>0.3.0

### Frontend
* Complete change of terminology from dapps to blockchain applications.
* Implemented feeService. Fetching transactions fees for each transaction type.
* Adding security warning before opening apps.
* Closed [#9](https://github.com/LiskHQ/lisk/issues/9). Disabling buttons on first click. Adding success/error toasts.
* Closed [#14](https://github.com/LiskHQ/lisk/issues/14). Explaining master passphrase.
* Closed [#17](https://github.com/LiskHQ/lisk/issues/17). Fixing Safari font-weight / aliasing.
* Fixed [#31](https://github.com/LiskHQ/lisk/issues/31). Updating bitcore-mnemonic [@mrv777](https://github.com/mrv777).
* Fixed [#38](https://github.com/LiskHQ/lisk/issues/38). Including total count of delegates.

### Backend
* Updated transaction fees. 25 LSK for Delegate and Dapp registrations.
* Change of blockchain application categories
* Moved large queries into postgresql views
* Extracted SQL logic into separate modules
* Closed [#134](https://github.com/LiskHQ/lisk/issues/134) Adding ```GET /api/blocks/getFees``` endpoint.
* Closed [#137](https://github.com/LiskHQ/lisk/issues/137) Adding ```GET /api/blocks/getNethash``` endpoint.
* Standardised and fixed up test-suite.
* TBC

### Build
* installLisk.sh — added mainnet vs testnet installation.
* installLisk.sh — laying framework for upgrade support.
* tune.sh — corrected bsd memory allocation.

### Documentantion
* lisk-docs — Added prereq document.
* lisk-docs — Added upgrade document.
* lisk-docs — Added instructions for mainnet installation.

# <a name="023"></a>0.2.3

### Build
* Fixed [#76](https://github.com/LiskHQ/lisk/issues/76). Updating node/lisk-node to 0.12.14.
* Improvements to: installLisk.sh & lisk.sh: [@Isabello](https://github.com/Isabello)
  * Reducing ram usage on machines with less than 1024Mb RAM.
  * Made further reliability improvements to process management.
  * Fixing postgresql locale / character encoding issues.
* Platforms available with this release: Linux-x86_64, Linux-i686, Linux-armv6l, Linux-armv7l, FreeBSD-amd64 and Darwin-x86_64.
* The official docker image will also be updated soon.

### Backend
* Completed work towards [#82](https://github.com/LiskHQ/lisk/issues/82), fork cause 3: [@karmacoma](https://github.com/karmacoma)
  * Removing use of setImmediate in round ticks.
  * Scoping each invocation of RoundPromiser.
  * Iterating over delegates asynchronously.
  * Getting outsiders only at end of round.
  * Fixing finishRound logic.
* Fixed [#131](https://github.com/LiskHQ/lisk/issues/131). Added nethash p2p verification. [@fix](https://github.com/fix)
* Fixed [#22](https://github.com/LiskHQ/lisk/issues/22). Cannot read property ‘senderPublicKey’ of undefined. [@fix](https://github.com/fix)
* Fixed forced blocks verification on startup, i.e: config.json-loading-verifyOnLoading.
* Closed [#126](https://github.com/LiskHQ/lisk/issues/126). Using recommended pg-promise approach. [@vitaly-t](https://github.com/vitaly-t)

# <a name="022"></a>0.2.2

### Build
* Added lisk.sh reload command. [@Isabello](https://github.com/Isabello)
* Fixed [#6](https://github.com/LiskHQ/lisk/issues/6). lisk.sh restart now cycles both Node.js and Postgresql. [@Isabello](https://github.com/Isabello)
* Fixed [#10](https://github.com/LiskHQ/lisk/issues/10). lisk.sh start/stop/restart now work more reliably. [@Isabello](https://github.com/Isabello)
* New simpler binary installation, thanks to liskInstall.sh. [@Isabello](https://github.com/Isabello)
* Added tune.sh for optimizing the default postgresql.conf. [@Isabello](https://github.com/Isabello)
* Preliminary support for checksummed archives. [@Isabello](https://github.com/Isabello)
* Platforms available with this release: Linux-x86_64, Linux-i686, Linux-armv6l, Linux-armv7l, FreeBSD-amd64 and Darwin-x86_64.
* The official docker image will also be updated soon.

### Backend
* Completed work towards [#82](https://github.com/LiskHQ/lisk/issues/82), fork cause 3: [@karmacoma](https://github.com/karmacoma)
  * Heavy refactoring of Round#tick, Round#backwardTick.
  * Memory table updates are now wrapped within db transactions.
  * Added checks for missed/unapplied mem_rounds on startup.
  * Dropping mem_rounds table on reload if not in a valid state.
  * Skipping delegate slot when round is ticking.
  * Don’t receive block when round is ticking.
* Fixed pending transactions API endpoint. [@fix](https://github.com/fix)
* Fixed [#8](https://github.com/LiskHQ/lisk/issues/8). Delegate usernames must now be lowercase. [@fix](https://github.com/fix)
* Fixed [#40](https://github.com/LiskHQ/lisk/issues/40). API payloads are now limited to 2Mb per request. [@fix](https://github.com/fix)
* Fixed ip address detection when using proxy. [@Isabello](https://github.com/Isabello)
* Fixed [#122](https://github.com/LiskHQ/lisk/issues/122). Corrected schema errors in dapp transfers. [@TheGoldenEye](https://github.com/TheGoldenEye)
* Fixed [#101](https://github.com/LiskHQ/lisk/issues/101), [#107](https://github.com/LiskHQ/lisk/issues/107) productivity calculations. [@mrv777](https://github.com/mrv777)
* Fixed [#90](https://github.com/LiskHQ/lisk/issues/90). Translating ips from long. [@cezarsn](https://github.com/cezarsn)

### Frontend
* Fixed non-functioning delegate registration. [@2mdoty](https://github.com/2mdoty)
* Fixed [#34](https://github.com/LiskHQ/lisk/issues/34). Dapp registration when 2nd passphrase enabled.
* Fixed [#43](https://github.com/LiskHQ/lisk/issues/43). Language switcher now works for all languages. [@senikk](https://github.com/senikk)

# <a name="021"></a>0.2.1

### Build
* PostgreSQL is now included with the “Binary” install, removing the need to install it separately. A simple ```bash lisk.sh coldstart``` will initialise the database on first start.
* Running ```lisk.sh``` as root is now prevented by default.
* Platforms available with this release: Linux-x86_64, Linux-i686, Linux-armv6l, Linux-armv7l, FreeBSD-amd64 and Darwin-x86_64.
* The official docker image has also been updated: https://github.com/LiskHQ/lisk-docker

### Backend
* Closed [#69](https://github.com/LiskHQ/lisk/issues/69). Loading schema using external SQL file [@vitaly-t](https://github.com/vitaly-t).
* Closed [#84](https://github.com/LiskHQ/lisk/issues/84). Allowing the setup of logging path in config.json [@TheGoldenEye](https://github.com/TheGoldenEye).
* Fixed [#77](https://github.com/LiskHQ/lisk/issues/77). Peers API endpoint now works when filtered by state [@slasheks](https://github.com/slasheks).
* Fixed all known casting issues caused by db migration.
* Fixed ‘Recipient not found’ error on virgin accounts.
* Improved error logging/comments on fork causes.
* Added proper delegate username validations.
* Fixed test coverage of delegates API.

### Frontend
* Fixed [#30](https://github.com/LiskHQ/lisk-ui/issues/30). Voting now possible after enabling 2nd passphrase [@pilldriver](https://github.com/pilldriver).
* Fixed [#29](https://github.com/LiskHQ/lisk-ui/issues/29). Resetting application state between sessions [@2mdoty](https://github.com/2mdoty).
* Fixed [#13](https://github.com/LiskHQ/lisk-ui/issues/13). Improved error handling when sending transactions [@karek314](https://github.com/karek314).
* New and improved Russian translation [@densmirnov](https://github.com/densmirnov).
* Refactored delegate username validations.

# <a name="020"></a>0.2.0

### Backend
* Changed database engine from SQLite to [PostgreSQL](http://www.postgresql.org/). Providing faster query performance, better support for concurrency, and further options for scalability.
* Removed usernames and contacts from mainchain (to be later reimplemented as a separate Identity Dapp sidechain). Delegate usernames still remain.
* Added dapp zip link storage mechanism, replaces GitHub and Sia integration, with alternative decentralized solutions to be implemented in future releases.
* Implemented concatenated inserts/updates, dramatically reducing number of round trips between client and database: https://github.com/vitaly-t/pg-promise/wiki/Performance-Boost
* Implemented promise based database logic using: https://github.com/vitaly-t/pg-promise
* Added optional PostgreSQL event monitoring using: https://github.com/vitaly-t/pg-monitor (see: config.json:db.logEvents). This will be used for finding further efficiency improvements at the database level.
* Enabled gzip compression on all http requests using: https://github.com/expressjs/compression. Significantly reducing the size of payloads transmitted between peers on the network, and also for lisk-ui (Example: vendor_app.js : Without compression 5.4MB, With compression: 1.2MB).
* Improved syncing reliability and chain comparison efficiency between peers, through query and code refactoring of Blocks#getIdSequence and the /peer/blocks/common API endpoint.
* Accounts#getDelegate(s): Calculating approval rating from total supply rather than a static amount.
* Increased max transactions per block from 10 to 25 (subject to further change after more testing and efficiency improvements have been made).
* Changed peers communication format from CSV to JSON.
* Fixed DApps#getInstalledIds, filtering installed ids to only include numerically named folders.
* Fixed “Dapp not ready” messages when auto-launching dapps upon starting client.
* Closes [#24](https://github.com/LiskHQ/lisk/issues/24). Changing ‘sync’ to ‘syncing’. [@HeisenbergCoin](https://github.com/HeisenbergCoin)
* Closes [#33](https://github.com/LiskHQ/lisk/issues/33). Logging each client request. [@slasheks](https://github.com/slasheks)
* Fixes [#36](https://github.com/LiskHQ/lisk/issues/36). Adding username and publicKey properties. [@fix](https://github.com/fix)
* Fixes [#47](https://github.com/LiskHQ/lisk/issues/47). Changing timestamps to UTC. [@TheGoldenEye](https://github.com/TheGoldenEye)
* Fixed [#50](https://github.com/LiskHQ/lisk/issues/50). Indicating forged blocks more clearly. [@punkrock](https://github.com/punkrock)
* Fixes [#52](https://github.com/LiskHQ/lisk/issues/52). Removing virgin field from mem_accounts. [@simonmorgenthaler](https://github.com/simonmorgenthaler)
* Fixes [#54](https://github.com/LiskHQ/lisk/issues/54). Restricting total number of votes to 101. [@TheGoldenEye](https://github.com/TheGoldenEye)
* Fixes [#55](https://github.com/LiskHQ/lisk/issues/55). Fixing circular reference.
* Updated all 3rd party node modules to latest compatible versions.
* Switched from zip to gzipped tar for release packaging.
* Generated new genesis block for use on open testnet.

### Frontend
* Added translations for 10 languages (Greek, Spanish, French, Hungarian, Italian, Japanese, Norwegian, Portuguese, Romanian, Ukrainian).
* Updated translations for 4 languages (Chinese, Russian, German, Dutch).
* Enforced BIP39 passphrases.
* Enforced BIP39 second passphrases.
* Unified every modal.
* Improved Dapp registration and Multi-signature registration modals.
* Added fees overview to every modal.
* Added more descriptions to every modal.
* Removed usernames and contacts (to be later reimplemented as a separate Identity Dapp sidechain).
* Improved and unified the overall user interface.

# <a name="014"></a>0.1.4

* Imposing hard limit on number of transactions per block.
  * The previous limit of 100 was only checked during block verification, after a block has already been generated. Now only the last 10 unconfirmed txs in a given delegate’s stack will be included.

# <a name="013"></a>0.1.3

* Fixed [#45](https://github.com/LiskHQ/lisk/issues/45). Improved sync / block insertion rate.
* Fixed [#3](https://github.com/LiskHQ/lisk/issues/3). Setting X-Frame-Options/CSP headers [@fix](https://github.com/fix).
* Improved logging of received unconfirmed transactions.
* Improved logging of blocks loading from peer.

### Binary Install:
* Updated bundled SQLite to version 3.12.1.
* Fixed address in use errors on restart.

# <a name="012"></a>0.1.2
* Allowing dapps installation from GitHub using https.
* Fixed [#13](https://github.com/LiskHQ/lisk/issues/13). Checking for presence of recipientId [@fix](https://github.com/fix).
* SSL: Using the default cipher from recent nodejs version to protect against weak RC4 cipher [@TheGoldenEye](https://github.com/TheGoldenEye).
* Fixed unrecoverable fork when comparing delegate id to generator id.

# <a name="011"></a>0.1.1
* Multi-language user interface, initially with support for Chinese and German.
* Implemented forging reward offset (first reward starts on block 60480).
* Revised error and logs messages throughout all backend modules.
* Change of address format (addresses now end with an L).

# <a name="010"></a>0.1.0
* Complete rebranding of the client UI.
* Complete clean-up of the old code base.
* Fixed several browser specific UI bugs and inconsistencies.
* You can no longer add yourself to the contact book.
* Changed the transaction fee to a constant 0.1 LISK.
* Implemented Forging Rewards.
