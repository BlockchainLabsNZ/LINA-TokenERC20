# Gas consumption report
performed by Blockchain Labs, 6 April, 2018

```
Contract: TokenERC20
    total supply
      √ returns the total amount of tokens
    balanceOf
      when the requested account has no tokens
        √ returns zero
      when the requested account has some tokens
        √ returns the total amount of tokens
    transfer
      when the recipient is not the zero address
        when the sender does not have enough balance
          √ reverts (27733 gas)
        when the sender has enough balance
          √ transfers the requested amount (53295 gas)
          √ emits a transfer event (53295 gas)
      when the recipient is the zero address
        √ reverts (24108 gas)
    approve
      when the spender is not the zero address
        when the sender has enough balance
          √ emits an approval event (48746 gas)
          when there was no approved amount before
            √ approves the requested amount (48746 gas)
          when the spender had an approved amount
            √ approves the requested amount and replaces the previous one (33746 gas)
        when the sender does not have enough balance
          √ emits an approval event (48746 gas)
          when there was no approved amount before
            √ approves the requested amount (48746 gas)
          when the spender had an approved amount
            √ approves the requested amount and replaces the previous one (33746 gas)
      when the spender is the zero address
        √ approves the requested amount (47466 gas)
        √ emits an approval event (47466 gas)
    transfer from
      when the recipient is not the zero address
        when the spender has enough approved balance
          when the owner has enough balance
            √ transfers the requested amount (52161 gas)
            √ decreases the spender allowance (52161 gas)
            √ emits a transfer event (52161 gas)
          when the owner does not have enough balance
            √ reverts (28932 gas)
        when the spender does not have enough approved balance
          when the owner has enough balance
            √ reverts (31367 gas)
          when the owner does not have enough balance
            √ reverts (28932 gas)
      when the recipient is the zero address
        √ reverts (25306 gas)
    Contract: Ownable
      √ should have an owner
      √ changes owner after transfer (37781 gas)
      √ should prevent non-owners from transfering (25181 gas)
      √ should guard ownership against stuck state (26981 gas)
    burn
      when the given amount is not greater than balance of the sender
        √ burns the requested amount (49930 gas)
        √ emits a burn event (49930 gas)
      when the given amount is greater than the balance of the sender
        √ reverts (24203 gas)


·--------------------------------------------------------------------|-----------------------------------·
│                                Gas                                 ·  Block limit: 17592186044415 gas  │
·····································|·······························|····································
│  Methods                           ·          21 gwei/gas          ·          383.00 usd/eth           │
···············|·····················|·········|·········|···········|··················|·················
│  Contract    ·  Method             ·  Min    ·  Max    ·  Avg      ·  # calls       ·  usd (avg)     │
···············|·····················|·········|·········|···········|··················|·················
│  TokenERC20  ·  approve            ·  33746  ·  48746  ·    44676  ·    8  ·          0.36           │
···············|·····················|·········|·········|···········|··················|·················
│  TokenERC20  ·  burn               ·  24203  ·  49930  ·    41354  ·    3  ·          0.33           │
···············|·····················|·········|·········|···········|··················|·················
│  TokenERC20  ·  transfer           ·  24108  ·  53295  ·    39608  ·    4  ·          0.32           │
···············|·····················|·········|·········|···········|··················|·················
│  TokenERC20  ·  transferFrom       ·  25306  ·  52161  ·    38717  ·    7  ·          0.31           │
···············|·····················|·········|·········|···········|··················|·················
│  TokenERC20  ·  transferOwnership  ·  25181  ·  37781  ·    29981  ·    3  ·          0.24           │
···············|·····················|·········|·········|···········|··················|·················
│  Deployments                       ·                               ·  % of limit    ·                   │
·····································|·········|·········|···········|··················|················
│  TokenERC20                        ·      -  ·      -  ·  5624349  · 0 %  ·         45.24          │
·------------------------------------|---------|---------|-----------|------------------|----------------·

  29 passing

```

<br>

## Summary  
Upon finalization of the contracts to be used by LINA, the contracts were assessed on the gas usage of each function to ensure there aren't any unforeseen issues with exceeding the block size GasLimit.

<br>
