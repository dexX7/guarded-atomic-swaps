UC-Client-2: Prepare funding
----------------------------

  The locked destination is going to be funded with tokens.

  This use-case describes the process of preparing a raw transaction to
  fund the previously generated destination with tokens.

##### Scope:

- Swap client

##### Level:

- User-goal

##### Primary actor:

- Seller

##### Supporting actors:

- *None*

##### Preconditions:

  1. The seller configured the system's settings to connect to a running Omni Core RPC server
  2. The seller generated a script locked destination (UC-Client-1)

##### Main success scenario:

  1. The seller requests to prepare a funding transaction
  2. The seller provides a source address to spend from, the funding destination, an identifier of the tokens to lock, and the amount of tokens to lock
  3. The system creates a signed raw simple send transaction based on the specified data, with some extra bitcoins sent to the destination as reference amount
  4. The system determines the output to the script locked destination
  5. The system returns the signed raw simple send transaction `rawtx`, as well as the reference `output` to the locked destination, consisting of `txid`, `vout`, `scriptPubKey` and `value`

##### Extensions:

4a. The system fails to create a raw simple send transaction based on the specified data (e.g. due to too low balance):

  1. The system indicates the failure
  2. The use-case ends

##### Success guarantee:

  1. The system generated a signed raw funding transaction
  2. The seller has enough tokens and bitcoins to cover the funding transaction
  3. The funding transaction carries enough bitcoin as reference amount for at least one transaction sent from the script locked destination

---

- [To next page](uc-client-3_sign_transaction_stub.md)
- [To previous page](uc-client-1_create_destination.md)
- [Back to overview](../README.md)
