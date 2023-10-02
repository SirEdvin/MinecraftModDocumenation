# KV Storage

!!! picture inline end "KV Storage"
    ![KV Storage](kv_storage.png)
    Name: `kv_storage`

??? info "Supported versions"
    **Forge**: 1.20.x
    **Fabric**: 1.20.x


KV Storage is a simple implementation of a key-value database for your CC:T programs. It **is** owner-based, bound to the player who placed the block, so each KV storage that player placed is attached to the same database. 

Internally, KV storage by default uses `sqlite` database, attached to the world folder. If the server owner wants to disable only the KV storage database, they can change `kvStorageMode` to `DISABLED`. Also, each player has a limited number of keys stored inside the database, which is controlled by `kvStorageKeyLimit` and equal to 1000 by default.

## Supported APIs

- [Configuration API](configuration.md): provides `keyLimit` which shows the max number of keys player can have and `valueLimit` which shows max size of value.

## Functions

### put
`put(key: string, value: string, expire?: number)`

Put new key into KV storage. `expire` is optional argument that can be provided to make key automatically expire after some period of time. `expire` should be utc timestamp of real time, you can get it from `os.epoch("utc")` function.

```lua
put("key1", "v1") -- saving key1 into database
put("key2", "v1", os.epoch("utc") + 20) -- saving key2 into database, key2 will be expired after 20 seconds

```

---

### get

`get(key: string): string or null`

Helps you to retrive value from key, if key is present in database and not expired.

---

### delete
`delete(key: string)`

Removes key from database if it existed.

---

### list
`list(): table`

Returns a list of all available keys for owner.

---

### get_ext
`get_ex(key: String): number or nil`

Returns point in time when this key would expire. Nil if key is not present or expire is nil.

---

### put_ex

`put_ex(key: String, expire?: number or nil)`

Put new expire mark for key. You also can pass nil to remove expire from key.

---


