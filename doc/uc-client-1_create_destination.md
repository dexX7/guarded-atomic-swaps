UC-Client-1: Create destination
-------------------------------

  To simulate the properties of an output-based system, funds are going
  to be locked with a m-of-m multi-signature script, based on a key from
  the seller and a new and unique key from an oracle. The oracle will
  allow only one single signing operation to ensure no tokens from the
  locked destination can be double-spent.

  This use-case describes the process of creating a 2-of-2
  multi-signature script destination.

##### Scope:

- Swap client

##### Level:

- User-goal

##### Primary actor:

- Seller

##### Supporting actor:

- Oracle

##### Preconditions:

  1. The seller configured the system's settings to connect to a running Bitcoin or Omni Core RPC server
  2. The seller configured the system's settings to connect to a running oracle server

##### Main success scenario:

  1. The seller requests to generate a new lock-destination
  2. The seller provides a public key
  3. The system requests a new public key from the oracle
  4. The oracle generates and returns new and unique key-pair (UC-Oracle-1)
  5. The system sorts both keys
  6. The system creates a 2-of-2 multi-signature script, based on the sorted public keys
  7. The system returns the oracle's public key as `identifier`, and the `destination`, consisting of `address`, `pubkeys`, `redeemScript`, `reqSigs` and `type`

##### Extensions:

2a. The seller doesn't provide a public key:

  1. The system generates a new public key for the seller
  2. The use-case continues at 3

##### Success guarantee:

  1. The oracle generated a new and unique key-pair
  2. The system generated a 2-of-2 multisig script based on the seller's and oracle's public keys

##### Notes:

- Alternatively it is thinkable to support more than one public key, e.g. to allow 3-of-3, 4-of-4 etc., and to leverage multiple oracles

---

- [To next page](uc-client-2_prepare_funding.md)
- [Back to overview](../README.md)
