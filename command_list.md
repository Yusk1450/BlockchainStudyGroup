
# コマンドリスト

## Ethereumをインストールする（macOS）
１．[Homebrew](https://brew.sh/index_ja)をインストールする。  
２．下記のコマンドをターミナルに入力する。  
`brew tap ethereum/ethereum`  
`brew install ethereum`

## セットアップ
１．デスクトップに「eth」フォルダを作成する。  
２．「eth」フォルダに「genesis.json」を作成し、下記をコピペする。  
> {  
>   "config": {  
>     "chainId": 15  
>   },  
>   "nonce": "0x0000000000000042",  
>   "timestamp": "0x0",  
>   "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",  
>   "extraData": "",  
>   "gasLimit": "0x8000000",  
>   "difficulty": "0x4000",  
>   "mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000",  
>   "coinbase": "0x3333333333333333333333333333333333333333",  
>   "alloc": {}  
> }

３．Genesisブロックを作成する  
`geth --datadir ~/Desktop/eth init ~/Desktop/eth/genesis.json`

４．Gethを起動する  
`geth --networkid "15" --nodiscover --datadir "~/Desktop/eth" console 2>> ~/Desktop/eth/geth_err.log`

## Ethereumを体験してみる

１．Genesisブロックを確認する  
`eth.getBlock(0)`

２．アカウントを2つ作成する  
`eth.accounts`  
`personal.newAccount("パスワード")`  
`eth.accounts`  
`personal.newAccount("パスワード")`  
`eth.accounts`

３．採掘（マイニング）してみる  
`eth.coinbase`  
`miner.start()`  
`eth.blockNumber`  
`miner.stop()`  
`eth.getBalance(eth.accounts[0])`

４．送金してみる  
`eth.getBalance(eth.accounts[0])`  
`eth.getBalance(eth.accounts[1])`  
`personal.unlockAccount(eth.accounts[0])`  
`eth.sendTransaction({from: eth.accounts[0], to: eth.accounts[1], value: web3.toWei(5, "ether")})`  
`eth.getBalance(eth.accounts[1])`  
`personal.unlockAccount(eth.accounts[1])`  
`eth.sendTransaction({from: eth.accounts[1], to: eth.accounts[0], value: web3.toWei(3, "ether")})`  
`eth.getBalance(eth.accounts[1])`  
`eth.getTransaction(トランザクションID)`