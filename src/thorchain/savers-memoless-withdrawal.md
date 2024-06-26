# Savers/Earn memoless withdrawal

If you have a Savers/Earn position you wish to withdraw and are unable to use a
THORChain front-end (e.g. THORSwap), you can try a [memoless withdrawal].

This little-known feature of THORChain allows you to issue a withdrawal by
sending a small (yet very specific) amount to a special THORChain wallet
address.  No need for THORSwap or any other front-end.

**The below procedure withdraws 100% of your Savers/Earn position.  Please read
the procedure and the below chart _before_ performing any actions!**

1. Make sure whatever wallet you're using has the wallet address which opened the Savers/Earn position.  **This is super important!**
1. Visit <https://thornode.ninerealms.com/thorchain/inbound_addresses> and search for the THORNode chain name associated with your Savers/Earn asset (see below chart).
1. Extract the `address` field from the structure.  **This is the destination address you'll be sending a small amount to.**
   - The `address` field will change depending on which THORNode server you hit (it's random).  What's important is that you do the above 2 steps **every single time you want to do a memoless withdrawal**.  The addresses change regularly; sending funds to a deprecated/expired address will result in the loss of those funds.
1. In your wallet, send the required amount (see below) to the address obtained in the previous step.
   - **Only send the specific amount shown in the chart!**  A different amount (smaller or larger) can result in a partial withdrawal or loss of the sent amount.

| Savers Vault     | THORNode name | Amount for 100% withdrawal |
| ---------------- | ------------- | -------------------------- |
| ATOM             | GAIA          | 0.0001 ATOM                |
| AVAX             | AVAX          | 0.0001 AVAX                |
| BCH              | BCH           | 0.0002 BCH                 |
| BNB (BEP20/BSC)  | BSC           | 0.0001 BNB (BEP20)         |
| BTC              | BTC           | 0.0002 BTC                 |
| DOGE             | DOGE          | 1.0001 DOGE                |
| ETH              | ETH           | 0.0001 ETH                 |
| LTC              | LTC           | 0.0002 LTC                 |
| USDC (AVAX)      | AVAX          | 0.0001 AVAX                |
| USDC (ERC20)     | ETH           | 0.0001 ETH                 |
| USDT (ERC20)     | ETH           | 0.0001 ETH                 |

[1]: https://dev.thorchain.org/saving-guide/quickstart-guide.html#basic-mechanics
