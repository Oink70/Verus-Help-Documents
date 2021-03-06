HOW-TO Shielding Verus Coin via the CLI:

You must first "shield coins" (send from a transparent Raddr to a shielded zaddr) to be able to use them in staking, when they first unlock.
This is part of the Zcash protocol itself. The commands below assume you are in the Verus source code directory

cd src/
./fiat/verus z_shieldcoinbase

You can either use an existing zaddr or use a new zaddr. To make a new zaddr:

./fiat/verus z_getnewaddress

Use the address the above command outputs in the z_shieldcoinbase command

To shield all coinbase in your wallet, you can use "*" (quotes are important) and zaddr that is getting the funds:

./fiat/verus z_shieldcoinbase "*" zcdZ7Ja5d6Nse9wbaQoMVRcJW2pJScWwQ9Kv2ohX7UPakohLpK3BwTi1ksxiEXXj8wxtuK4rq7MDeUsNFxtrFjcApwyoXXX

To just shield a single address, specify that as the first argument:

./fiat/verus z_shieldcoinbase RUWC2P9f39a4x4p4tDeN5B6VbhRiNPSbzz zcdZ7Ja5d6Nse9wbaQoMVRcJW2pJScWwQ9Kv2ohX7UPakohLpK3BwTi1ksxiEXXj8wxtuK4rq7MDeUsNFxtrFjcApwyoXXX

Once the funds have moved to the zaddr and are confirmed, you can freely send them to any taddr, and they will be eligble for staking.

To send from a certain zaddr to a transparent address, use z_sendmany. The following command sends 10 Verus to a given transparent address.

TADDR=Ryouraddresss ./fiat/verus z_sendmany zcZpfuzzJqmNJ3fUJekvbnyuxuJe9eAURAHrMCvN2Nr7VuWjakb1LEw6j2etPcCnr45BRot7MaMbipuS5da162BfuUkFGxx "[{"address":"$TADDR","amount":10}]"
I have been developing it on this gist: https://gist.github.com/leto/e5ab28c5c5f85031b8b0f7b6bf7cf430

(submitted by @dukeleto)