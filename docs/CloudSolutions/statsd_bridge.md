# StatsD Bridge

!!! picture inline end "StatsD Bridge"
    ![StatsD bridge](statsd_bridge.png)
    Name: `statsd_bridge`

??? info "Supported versions"
    **Forge**: 1.20.x
    **Fabric**: 1.20.x

StatsD Bridge exists to allow players to send [statsd metrics](https://github.com/statsd/statsd/blob/master/docs/metric_types.md) to a preconfigured statsd server. The settings for this peripheral are split into two files.

The common configuration field `enableStatsDBridge` corresponds to the enabled peripheral block, while the server configuration section `statsd` is responsible for statsd bridge configuration.

The server owner should configure `statsdHostname` and `statsdPort` and point them to some statsd receiver and set `enableStatsDConnection` to true. With these settings, at the start of the server, a new non-blocking statsd client will be started. The server owner can also define a `statsdPrefix` which will be added to the name of any metrics at start.

Any metric that a player will send with this integration will always start with a preconfigured `statsdPrefix` and will also contain the owner's name. So, it would be `<prefix><owner_name>.aspect`. The owner is a player who placed the block. Owner is also used for rate limiting messages to the statsd client; the max amount of messages per minute is controlled by `statsdPlayerRateLimit`. This is also a global rate limit per minute, which is controlled by `statsdGlobalRateLimit`.

## Supported APIs

- [Configuration API](configuration.md): provides `playerRateLimit` and `globalRateLimit` which tells you how often you are allowed to send values per minute.


## Functions

### count
`count(aspect: String, delta: number)`

Will send [counter](https://github.com/statsd/statsd/blob/master/docs/metric_types.md#counting) to statsd server. Delta can be any real number.

---

### delta
`delta(aspect: String, delta: number)`

Function send [gauge](https://github.com/statsd/statsd/blob/master/docs/metric_types.md#gauges) delta to statsd server. Delta can be any real number.

---

### gauge
`gauge(aspect: String, value: number)`

Function sets [gauge](https://github.com/statsd/statsd/blob/master/docs/metric_types.md#gauges) value to stastd server. It **is** takes to account that you can't set negative value for gauge as one message, so it will actually send two messages, one with setting gauge to zero, and one with negative delta.

---

### set
`set(aspect: String, eventName: String)`

Functions that sets some [aspect](https://github.com/statsd/statsd/blob/master/docs/metric_types.md#sets) to same value. Should accept anything

---

### time
`time(aspect: String, timeInMs: number)`

Function that sends [time](https://github.com/statsd/statsd/blob/master/docs/metric_types.md#timing) measurement to statsd server. `timeInMs` supposed to be time in milliseconds. Please, take to account, that `os.epoch()` and `os.date()` by default returns Minecraft time, so to measure execution time you should do something like this:

```lua
local p = peripheral.find("statsd_bridge")
local start_time = os.epoch("utc")
some_function()
p.time("some_function", os.epoch("utc") - start_time)
```
