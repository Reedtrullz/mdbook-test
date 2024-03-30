# Tracking a swap

## Procedure

1. Find the Transaction Hash/ID of your THORSwap activity: click the Transaction History button in the upper right of THORSwap and then choose View Details
   - If you still can't find your Transaction Hash/ID: try using [RuneScan] to search for your wallet address (either source or destination wallet) and find your transaction.  Once you find it, click on it and there should be an icon to copy the Transaction Hash/ID
1. Visit the [9R THORChain Tracker]
1. Enter the Transaction Hash/ID into the **Swap Transaction ID** search box at the top of the page
1. If your transaction is found, details about it will be shown, including an ETA
1. If your transaction **is not** found, then it's possible the transaction is still waiting for [inbound confirmations][1] on the THORChain network.  We sometimes call this the "inbound leg":
   - Tracking inbound confirmation counts is a little complicated and technical!
   - Visit `https://thornode.ninerealms.com/thorchain/tx/status/YOUR_TRANSACTION_HASH` in your browser
     - In the above link, replace `YOUR_TRANSACTION_HASH` with the Transaction Hash/ID from step #1
   - If successful, you should be shown a JSON blob (a bunch of technical data)
   - If you see the message `{"error":"rpc error: code = Unknown desc = internal"}` then the Transaction Hash/ID is wrong.  You may need to ensure the Transaction Hash/ID is in all lowercase
   - Look through the structured data for a small section called `stages`.  There are sub-sections called `inbound_observed` and `inbound_confirmation_counted` which are related to inbound confirmations
   - Examine the `inbound_finalised` section:
     - If the `completed` field is `false`, then the inbound leg is still in progress (see above)
     - If the `completed` field is `true`, then your transaction **is not** stuck in the inbound leg (possibly it just went through!)

If you're still having problems, ask for help in the THORSwap Discord channel `#thorswap-general` where THORSwap community moderators can help.  If you prefer official THORSwap staff support which is one-on-one and private, open a ticket in the `#support-desk` channel and be patient.

[1]: https://crypto-university.medium.com/under-the-hood-thorchain-transaction-delays-250d00ed57b7#f667
{{#include ../LINKREFS.md}}
