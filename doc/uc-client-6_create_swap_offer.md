UC-Client-6: Create swap offer
------------------------------

  To prepare an atomic swap, the seller extends the transaction stub
  with a transaction output to a desired destination, and the payment
  amount. This output is the payment output to the seller.

  The  transaction is then signed with the signature hash flags
  `"SINGLE|ANYONECANPAY"`, which "seals" the payment output, while
  still allowing to add further inputs or outputs. However, a potential
  buyer can't remove the payout output, which ensures the seller
  receives the desired coins in exchange, if the swap is finalized.

  This use-case describes the process of creating an atomic swap offer.

##### Scope:

- Swap client

##### Level:

- User-goal

##### Primary actor:

- Seller

##### Supporting actors:

- *None*

##### Preconditions:

  1. The seller configured the system's settings to connect to a running Bitcoin or Omni Core RPC server
  2. The seller created and verified a signed transaction stub (UC-Client-3)
  3. The seller previously funded a script locked destination with tokens (UC-Client-4)

##### Main success scenario:

  1. The seller requests to prepare an atomic swap offer
  2. The seller provides the transaction stub signed by the oracle, it's transaction inputs (i.e. the hash of the signed funding transaction, the index of the funding output to the script lock destination, the corresponding scriptPubKey and the redeemScript for the locked destination), a destination to send the coins to, and specifies the amount of coins desired in exchange for the tokens
  3. The system adds an output to the transaction stub, with the seller's specified destination and payment amount
  4. The system signs the transaction with the signature hash flag `"SINGLE|ANYONECANPAY"`
  5. The system returns the updated and signed raw transaction

##### Extensions:

4a. The system fails to sign the transaction

  1. The system indicates the failure
  2. The use-case ends

##### Success guarantee:

  1. The transaction stub was extended with a payment output to the seller
  2. The payment output can't be removed or modified, without invalidating the transaction

---

- [To next page](uc-client-7_accept_swap_offer.md)
- [To previous page](uc-client-5_unlock_tokens.md)
- [Back to overview](../README.md)
