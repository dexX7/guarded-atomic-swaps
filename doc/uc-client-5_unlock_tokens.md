UC-Client-5: Unlock tokens
--------------------------

  If the seller decides to cancel a swap and simply wants to unlock the
  script locked tokens, then a simple send back to the seller can be
  created.

  This use-case describes the process of unlocking tokens without
  executing an atomic swap.

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
  2. The seller created and verified a signed transaction stub (UC-Client-3)
  3. The seller previously funded a script locked destination with tokens (UC-Client-4)

##### Main success scenario:

  1. The seller requests to unlock tokens
  2. The seller provides the transaction stub signed by the oracle, it's transaction inputs (i.e. the hash of the signed funding transaction, the index of the funding output to the script lock destination, the corresponding scriptPubKey and the redeemScript for the locked destination), and a destination to send the tokens to
  3. The system determines the identifier and amount of locked tokens
  4. The system adds a payload to the transaction stub, sending the previously determined amount of tokens (either as "simple send" or "send all")
  5. The system adds a reference output to the transaction stub, with the seller's specified destination, whereby the reference amount also serves to carry change
  6. The system signs the transaction with the signature hash flag `"ALL"`
  7. The system broadcasts the signed transaction
  8. The system returns the hash of the broadcasted transaction

##### Extensions:

3a. The system determines the locked destination has a zero balance

  1. The use-case continues at 5

6a. The system fails to sign the transaction

  1. The system indicates the failure
  2. The use-case ends

7a. The system fails to broadcast the funding transaction

  1. The system indicates the failure
  2. The use-case ends

##### Success guarantee:

  1. The tokens are unlocked and returned to the seller
  2. The script locked destination is considered as used

##### Notes:

- Alternatively the user may provide the payload to add to the transaction, to reduce the need for a fully synchronized chain

---

- [To next page](uc-client-6_create_swap_offer.md)
- [To previous page](uc-client-4_send_funding_transaction.md)
- [Back to overview](../README.md)
