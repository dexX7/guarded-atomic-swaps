API-Oracle-1: Get new and unique public key
-------------------------------------------

The oracle generates a new and unique public key, which can be used to
create a locked multi-signature script destination.

##### Endpoint:
```js
GET /getpubkey
```

##### Response:
```js
Status: 200 OK
```
```js
{
  "pubkey": "02684c357f3eac6ff86aa036e2edd2c20a1e1b79dacf37487843bd30311ae98512"
}
```

---

- [To next page](api-oracle-2_post_sign.md)
- [To previous page](uc-order-3_list_orders.md)
- [Back to overview](README.md)
