Contract exposes following functionality connected to transactions and tokens:
1) depositing
2) exiting
3) challenging exists
4) finalizing exits
5) adding new tokens

ad. 4 - watcher will need to know what is the address of the token it is exiting. finalizeExit now takes an argument - token address. BTW - do we need a story for that or is finalizeExit called by wallet code?

ad 1,2,3 - currency on the side of elixir code is handled as an address of the token (or 0x0 value for ETH). This address stored in `cur12` field in the transaction body. Affected API calls and exposed datastructures:

* Transaction.new/2 -> Transaction.new/3
* %Transaction{} has new field - `cur12`

