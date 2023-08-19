# `ping` - send ICMP ECHO_REQUEST packets to network hosts

## `ping -noqc max_times [-t max_timeout_in_seconds] host`

```sh
% ping -noc3 -t3 192.168.1.2
PING 192.168.1.2 (192.168.1.2): 56 data bytes
Request timeout for icmp_seq 0
ping: sendto: No route to host
Request timeout for icmp_seq 1

--- 192.168.1.2 ping statistics ---
3 packets transmitted, 0 packets received, 100.0% packet loss
```

```sh
% ping -noc3 -t3 192.168.1.3
PING 192.168.1.3 (192.168.1.3): 56 data bytes
64 bytes from 192.168.1.3: icmp_seq=0 ttl=64 time=83.386 ms

--- 192.168.1.3 ping statistics ---
1 packets transmitted, 1 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 83.386/83.386/83.386/0.000 ms
```

## Options

|Option|Description|Example
|-|-|-
|`n`|Don't translate IP to name|`-n`
|`o`|Stop immediately after receiving a reply|`-o`
|`q`|Quiet - Ouput summary only
|`c max_times`|Stop after a particular times|`-c3`
|`t max_timeout_in_seconds`|Stop after running in the specified seconds|`-t3`