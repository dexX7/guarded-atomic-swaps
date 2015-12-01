API-Oracle-2: Sign transaction stub
-----------------------------------

The oracle signs the given transaction with the key, corresponding to
the provided public key, which was used to create the script locked
destination.

The locking key is only used one single time to sign a transaction, and
subsequent signing requests are rejected.

Requests to sign transactions, which are not fully dependent on the
oracle, i.e. inputs must refer to m-of-m multi-signature scripts,
where the oracle is a signatory, are rejected.

Malformed requests are also rejected.

##### Endpoint:
```js
POST /sign
```

##### Request:
```js
{
  'rawtx': '010000000163f6319eacb2ac1652a766d3c7c9e26196e6303e1df3da224c31e2ca19a148a20200000000ffffffff0000000000',
  'prevtxs': [{
    'redeemScript': '522102aac0a015a8847225e585fff3f541532854297f9f0baec0b016bd916ee76138592103ca8aa2f4f98764e0e7e7e1e85beb771a7157e3e858daa841b1df0b218fe7f50852ae',
    'scriptPubKey': 'a9140cf80cc8eef0214d70cd71bb202ddf830a30e49687',
    'vout': 2,
    'txid': 'a248a119cae2314c22daf31d3e30e69661e2c9c7d366a75216acb2ac9e31f663'
  }],
  'sighashtype': 'NONE|ANYONECANPAY',
  'key': '02aac0a015a8847225e585fff3f541532854297f9f0baec0b016bd916ee7613859'
}
```

##### Response:
```js
Status: 200 OK
```
```js
{
  'hex': '010000000163f6319eacb2ac1652a766d3c7c9e26196e6303e1df3da224c31e2ca19a148a2020000009200483045022100dd18182ccd47cc5d63c2424be87c1a43038a87888769bfb64bf898f65b6422120220405fc8879abd644565e7984ef230424f9eace4427dae7ce6209aa3b438767bf08247522102aac0a015a8847225e585fff3f541532854297f9f0baec0b016bd916ee76138592103ca8aa2f4f98764e0e7e7e1e85beb771a7157e3e858daa841b1df0b218fe7f50852aeffffffff0000000000',
  'complete': false
}
```

---

If the signing key was previously used, the request is rejected:

##### Response:
```js
Status: 403 Forbidden
```
```js
{
  'error': 'key already used'
}
```

---

If the signing key doesn't refer to a key created by the oracle, the
request is rejected:

##### Response:
```js
Status: 403 Forbidden
```
```js
{
  'error': 'unknown key'
}
```

---

If the request is malformed, or the transaction to sign isn't fully
dependent on the oracle, the request is rejected:

##### Response:
```js
Status: 403 Forbidden
```
```js
{
  'error': 'invalid request'
}
```

##### Navigation:

- [To previous page](api-oracle-1_get_getpubkey.md)
- [Back to overview](README.md)
