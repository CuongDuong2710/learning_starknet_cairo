Compile

```sh
mkdir comp
starknet-compile src/ERC721_ex1.cairo --output comp/ERC721.json
```

Declare contact

```sh
starknet declare --contract comp/ERC721_ex1.json --wallet starkware.starknet.wallets.open_zeppelin.OpenZeppelinAccount
```

Deploy

```sh
starknet deploy --contract comp/ERC721_ex1.json --inputs <name> <symbol> <owner> --network alpha-goerli --no_wallet

Or:
starknet deploy --class_hash CLASH_HASH
```

starknet deploy --inputs 71942470984044 4279881 1113919593762118687475376511143865116397738250343892252580464580248600753728 --network alpha-goerli  --class_hash 0x566df6ea2502956a6185e076c01b567f5346b2ae5df81e1d6d4520fe6adf551 --contract artifacts/ERC721.json 

Error

> starknet: error: the following arguments are required: --class_hash

Create new account and deploy. Then can declare contract
```sh
starknet new_account

Account address: 0x05fce5a8de5ec129fa25a39e2bf989510528c5fefa2764b041802a0b21551990
Public key: 0x0493ef965a58be3577b84f93da81c7b7f351009befabc981467b9eb2f282a227
Move the appropriate amount of funds to the account, and then deploy the account
by invoking the 'starknet deploy_account' command.

NOTE: This is a modified version of the OpenZeppelin account contract. The signature is computed
differently.
```

```sh
(cairo_venv) cuongduong@CuongDuong:~/starknet-du/starknet-erc721/contracts$ starknet deploy_account

Sending the transaction with max_fee: 0.000000 ETH (548687436 WEI).
Sent deploy account contract transaction.

Contract address: 0x05fce5a8de5ec129fa25a39e2bf989510528c5fefa2764b041802a0b21551990
Transaction hash: 0x4dc0e562fb0a177cc7012ea5702b4a8a297fc3394acfdf060bcdde35283273c
```


```sh
(cairo_venv) cuongduong@CuongDuong:~/starknet-du/starknet-erc721/contracts$ starknet declare --contract comp/ERC721_ex1.json
Sending the transaction with max_fee: 0.000000 ETH (146098802 WEI).
Declare transaction was sent.
Contract class hash: 0x566df6ea2502956a6185e076c01b567f5346b2ae5df81e1d6d4520fe6adf551
Transaction hash: 0x4490250283c4dae852706d1be30acf0b00d3744cb3122a2f76336f9b6d2233
```

Python utils

```sh
$ python -i utils.py

>>> str_to_felt("Animal")
71942470984044

>>> str_to_felt("ANI")
4279881

>>> hex_to_felt("0x027674c615e5be1C960307C293BDBb5d675ED8955d2bF54B7ea0cc130792b640")
1113919593762118687475376511143865116397738250343892252580464580248600753728
```