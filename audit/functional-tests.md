# Functional tests
Tests are conducted on the Kovan test network. The following contract has been verified on Etherscan.

## [`TokenERC20 [0x4ef387]`](https://kovan.etherscan.io/address/0x4ef38712dd42b22c7e5a02b757f2209ed57ab5c1#code)

## Accounts

* Owner: [0x1d57eee78fc10c74eaf6f1793016fdcb16294529](https://kovan.etherscan.io/address/0x1d57eee78fc10c74eaf6f1793016fdcb16294529)
* SupplyReceiver: [0xe25650ee4c52b41eb517dd7579db3475f89caf55](https://kovan.etherscan.io/address/0xe25650ee4c52b41eb517dd7579db3475f89caf55)

## Expected behaviour tests

- [x] Cannot change controller of TokenERC20 if called by non-owner. [`0x4e5d28`](https://kovan.etherscan.io/tx/0x4e5d28760a14b1b677da038e41b80c9d70262591b17414155bb9aa2ba6253be5)
- [x] Owner can change controller of TokenERC20. [`0xfefb7f`](https://kovan.etherscan.io/tx/0xfefb7f722b3f3bd61c4db2d33ff70f4bc74449d73602d781b53d8315b2d06e85)
- [x] Token holders can successfully transfer tokens to specified addresses [`0x66b827`](https://kovan.etherscan.io/tx/0x66b827eb6483bc403366de91a1fc2d9ef5d90f69aa54d8661d25ec01d61ac882)
- [x] No tokens are burned or removed from totalSupply when calling burn from an address with 0 tokens. [`0x712100`](https://kovan.etherscan.io/tx/0x71210018705055c903cc11425eb491de05ad71e7dd45f6b53d80bec73dd4e234)
- [x] Successfully burn tokens and remove burned amount from totalSupply when called from a token holder. [`0x7cc083`](https://kovan.etherscan.io/tx/0x7cc08361bb1f63cf903ca1a2b9d9cc27e7f0b5091fbfcc428832d12c2c684ef1)
- [x] Successfully approve allowance amount of tokens that can be spent by set spender address. [`0x49c68f`](https://kovan.etherscan.io/tx/0x49c68fe8062dc19be278814ec3e83a89a53560b578f75af669b8750f59969f43)
- [x] Spender address cannot spend more tokens exceeding the set allowance. [`0x049a78`](https://kovan.etherscan.io/tx/0x049a7860db04d9a45dd5ae4e9652f20c11e5d6f67250d815c1219daf0ecb3032)
- [x] Spender address can successfully spend specified allowance amount of tokens. [`0xeb8260`](https://kovan.etherscan.io/tx/0xeb82607c6f9614ece753fea02f395d9a03959eda599102c24602934fde67090a)
