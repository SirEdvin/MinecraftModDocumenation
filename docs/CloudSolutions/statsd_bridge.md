# StatsD Bridge

!!! picture inline end "StatsD Bridge"
    ![StatsD bridge](statsd_bridge.png)
    Name: `statsd_bridge`

??? info "Supported versions"
    **Forge**: 1.20.x
    **Fabric**: 1.20.x

StatsD Bridge exists to allow players send [statsd metrics](https://github.com/statsd/statsd/blob/master/docs/metric_types.md) to preconfigured statsd server. Settings for this peripheral as split into two files.

Common configuration field `enableStatsDBridge` corresponds for enabled peripheral block, while server configuration section `statsd` are responsible for statsd bridge configuration.

Server owner should configure `statsdHostname` and `statsdPort` and point it to some statsd receiver and set `enableStatsDConnection` to true. With this settings at start of server, new statsd non-blocking client will be started. Server owner also can define a `statsdPrefix` which will be added to name of any metrics at start.

Any metric, that player will send with this integration would always start with preconfigured `statsdPrefix` and will also contain owner name. So, it would be `<prefix><owner_name>.aspect`. Owner is a player, whom placed block. Owner name would also be used for rate limiting of messages to statsd client, but this is **not implemented** right now.

## Supported APIs

- [Configuration API](configuration.md): will provide rate limiting information in future


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
