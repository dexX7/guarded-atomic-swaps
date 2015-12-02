UC-Oracle-2: Sign transaction stub
----------------------------------

  TODO

  This use-case describes the process of TODO

##### Scope:

- Oracle server

##### Level:

- Subfunction

##### Primary actor:

- Oracle

##### Supporting actor:

- Seller

##### Preconditions:

  1. TODO
  2. TODO

##### Main success scenario:

  1. The oracle provides the raw transaction to sign, the transaction inputs, the signature hash type and the public key to sign with
  2. The oracle checks, whether the signing key was used before
  3. The oracle checks, whether the signing key is known
  4. The oracle checks the transaction (TODO: more detail)
  5. The oracle requests to mark the key as used/dirty
  6. The system marks the key as used/dirty
  7. The oracle checks, whether the key is marked as used/dirty
  8. The oracle retrieves the corresponding private key
  9. The system returns the corresponding private key
  10. The oracle requests to sign the raw transaction
  11. The system signs the raw transaction
  12. The oracle returns the signed transaction

##### Extensions:

Xa. TODO

  1. TODO
  2. TODO

##### Success guarantee:

  1. TODO
  2. TODO

---

- [To next page](uc-order-1_publish_order.md)
- [To previous page](uc-oracle-1_create_key_pair.md)
- [Back to overview](../README.md)
