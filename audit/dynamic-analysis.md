# Dynamic Analysis
performed by Blockchain Labs, 6 April, 2018

```
  Contract: TokenERC20
    total supply
      √ returns the total amount of tokens
    balanceOf
      when the requested account has no tokens
        √ returns zero (106ms)
      when the requested account has some tokens
        √ returns the total amount of tokens
    transfer
      when the recipient is not the zero address
        when the sender does not have enough balance
          √ reverts (94ms)
        when the sender has enough balance
          √ transfers the requested amount (134ms)
          √ emits a transfer event (131ms)
      when the recipient is the zero address
        √ reverts (41ms)
    approve
      when the spender is not the zero address
        when the sender has enough balance
          √ emits an approval event (64ms)
          when there was no approved amount before
            √ approves the requested amount (86ms)
          when the spender had an approved amount
            √ approves the requested amount and replaces the previous one (80ms)
        when the sender does not have enough balance
          √ emits an approval event (53ms)
          when there was no approved amount before
            √ approves the requested amount (74ms)
          when the spender had an approved amount
            √ approves the requested amount and replaces the previous one (75ms)
      when the spender is the zero address
        √ approves the requested amount (79ms)
        √ emits an approval event (55ms)
    transfer from
      when the recipient is not the zero address
        when the spender has enough approved balance
          when the owner has enough balance
            √ transfers the requested amount (229ms)
            √ decreases the spender allowance (150ms)
            √ emits a transfer event (126ms)
          when the owner does not have enough balance
            √ reverts (40ms)
        when the spender does not have enough approved balance
          when the owner has enough balance
            √ reverts (95ms)
          when the owner does not have enough balance
            √ reverts (38ms)
      when the recipient is the zero address
        √ reverts
    Contract: Ownable
      √ should have an owner
      √ changes owner after transfer (76ms)
      √ should prevent non-owners from transfering (53ms)
      √ should guard ownership against stuck state (59ms)
    burn
      when the given amount is not greater than balance of the sender
        √ burns the requested amount (111ms)
        √ emits a burn event (84ms)
      when the given amount is greater than the balance of the sender
        √ reverts (42ms)


  29 passing

```
