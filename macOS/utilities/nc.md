# `nc` - arbitrary TCP and UDP connections and listens

Also `netcat`

A replacement for `telnet`.

## `nc -zw connection_timeout_in_seconds host port` - port scaning

`nc -zw3 192.168.1.121 31-200`

## Options

|Option|Description|Example
|-|-|-
|`z`|Send nodata for listening scan only|`-z`
|`G tcp_connection_timeout_in_secods`||`-G3`
|`w connection_timeout_in_seconds`||`-w3`
|`4`|Use IPv4 only|`-4`
|`6`|Use IPv6 only|`-6`