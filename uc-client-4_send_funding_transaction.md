UC-Client-4: Send funding transaction
-------------------------------------

  After the seller created a blank wild card transaction stub, and
  the oracle signed the transaction stub, the seller can be sure his or
  her tokens won't get lost, if they are sent to the locked
  destination. The funding transaction of UC-2 can then be broadcasted.

  This use-case describes the process of sending the funding
  transaction.

##### Scope:

- Swap client

##### Level:

- User-goal

##### Primary actor:

- Seller

##### Supporting actor:

- *None*

##### Preconditions:

  1. The seller configured the system's settings to connect to a running Bitcoin or Omni Core RPC server
  2. The seller prepared a funding transaction (UC-Client-2)
  3. The seller created and verified a signed transaction stub, which may be used to return the tokens (UC-3)

##### Main success scenario:

  1. The seller requests to send the funding transaction
  2. The system broadcasts the funding transaction
  3. The system confirms the send

##### Extensions:

2a. The system fails to broadcast the funding transaction

  1. The system indicates the failure
  2. The use-case ends

##### Success guarantee:

  1. The funding transaction was broadcasted and the tokens are now considered as locked

---

- [To next page](uc-client-5_unlock_tokens.md)
- [To previous page](uc-client-3_sign_transaction_stub.md)
- [Back to overview](README.md)
