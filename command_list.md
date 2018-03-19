
# コマンドリスト

## Ethereumをインストールする（macOS）
> brew tap ethereum/ethereum  
> brew install ethereum

## セットアップ
1. デスクトップに「eth」フォルダを作成する
1. 「eth」フォルダに「genesis.json」を作成し、下記をコピペする。
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

1. Genesisブロックを作成する
> geth --datadir /Users/ユーザ名/Desktop/eth init /Users/ユーザ名/Desktop/eth/genesis.json

1. Gethを起動する
> geth --networkid "15" --nodiscover --datadir "/Users/ユーザ名/Desktop/eth" console 2>> /Users/ユーザ名/Desktop/eth/geth_err.log

## Ethereumを体験してみる

1. Genesisブロックを確認する
> eth.getBlock(0)

1. アカウントを2つ作成する
> eth.accounts
> personal.newAccount("パスワード")
> eth.accounts
> personal.newAccount("パスワード")
> eth.accounts
