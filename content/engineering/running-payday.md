---
title: "Running Payday"
date: 2021-04-15T08:39:08-04:00
draft: false
---

Currently, our payday process is ran manually to ensure each week the automated process is working correctly. In the future (after [Glimesh/glimesh.tv#618](https://github.com/Glimesh/glimesh.tv/issues/618) is resolved), we should be able to run the process automatically.

## Running Payday Manually
The easiest way to run Payday is just to IEx into a web node, and run `Glimesh.PaymentProviders.StripeProvider.payout()`. However we don't run that ever, because we want to manually review the transfers that are scheduled for the week.

### Preparing Transfers
The `Transfers.prepare_payouts/0` function will return a list of TransferRequests that you can then use to commit the payout. The function does not preform any modifications, it just prepares the transfers for later.

```elixir
transfers = Glimesh.PaymentProviders.StripeProvider.Transfers.prepare_payouts()
```

After this you can run a couple of commands to verify the outputs. Please note the amounts are in cents.
```elixir
# Check the payout amount
Enum.sum(Enum.map(transfers, fn x -> x.transfer.amount end))

# Check the withholding amount
Enum.sum(Enum.map(transfers, fn x -> x.transfer.metadata.total_withholding_amount end))

# Check the number of transfers
length(transfers)
```

### Committing Transfers
After you have verified the amounts with their respective Stripe or DB entries, you can commit the transfer. 
```elixir
results = Glimesh.PaymentProviders.StripeProvider.Transfers.commit_payouts(transfers)
```
After this runs, it'll give you a list of `{:ok, stripe_transfer}` or `{:error, some_error}`. Any errors will also be printed to the error logger for easy visibility.