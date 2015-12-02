UC-Oracle-1: Create new and unique key-pair
-------------------------------------------

  This use-case describes the process creating a new key-pair and
  persisting it.

##### Scope:

- Oracle server

##### Level:

- Subfunction

##### Primary actor:

- Oracle

##### Supporting actor:

- Seller

##### Preconditions:

  1. The oracle configured the system's settings to connect to a running Bitcoin or Omni Core RPC server

##### Main success scenario:

  1. The oracle requests a new key-pair
  2. The system generates a key-pair
  3. The oracle checks, whether the key is valid
  4. The oracle checks, whether the key was not stored before
  5. The oracle checks, whether the key was not used to sign a transaction before
  6. The oracle requests to store the key
  7. The system stores the key
  8. The oracle checks, whether the key was stored
  9. The oracle returns the corresponding public key

##### Extensions:

Xa. TODO

  1. TODO
  2. TODO

##### Success guarantee:

  1. A new key-pair was generated
  2. A new key-pair was persisted
  3. The key-pair is unique and new
  4. The key-pair wasn't used before

##### Navigation:

- [To next page](uc-oracle-2_sign_transaction_stub.md)
- [To previous page](uc-client-7_accept_swap_offer.md)
- [Back to overview](../README.md)
