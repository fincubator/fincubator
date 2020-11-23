# Web3 telegram
###### description of telegram client modifications for managing decentralized services

Base client is https://github.com/fincubator/NekoX with PGP support by OpenKeychain

Now user can authentification by PGP keys in any telegram bot service

1. User create own key in OpenKeychain

![openkeychain](https://i.imgur.com/ErTMmwi.jpg)

2. User choose OpenPGP Provider: OpenKeychain

![](https://i.imgur.com/ifXGmFp.jpg)

3. User choose key from OpenKeychain

![](https://i.imgur.com/nZxK8wc.jpg)

4. Hold send button and Sing

![](https://i.imgur.com/wPro79D.png)

5. Owner recognized by bot

![](https://i.imgur.com/BRcD8VS.png)

Next level is ECDSA signing. Bitcoin, Ethereum and EOSIO support secp256k1 using Koblitz curve.

Cryptographic part like OpenKeychain, need modification for support ECDSA (please check this cryptographic method for support by openpgp-api of NekoX)

1. User need add ECDSA Provider EOS/EthereumKeychain and choose own keys

![](https://i.imgur.com/5Pw7Vtl.png)

2. When bot messaging like: 

> This message is not supported
> Download our fork URL
> {sign_transaction_button}x{EOS}x{"actions":[{"account":"cyber.domain","name":"biddomain","authorization":[{"actor":"d2153auxyftk","permission":"active"}],"data":{"bidder":"d2153auxyftk","name":"finteh","bid":"1.1000 CYBER"}}]}

Here {sign_transaction_button} - action for client, {EOS} - blockchain type and {"actions":[{"account":"cyber.domain","name":"biddomain","authorization":[{"actor":"d2153auxyftk","permission":"active"}],"data":{"bidder":"d2153auxyftk","name":"finteh","bid":"1.1000 CYBER"}}]} - transaction message for signing by active key of blockchain account d2153auxyftk

3. User see message like

![](https://i.imgur.com/BRImRV1.png)
