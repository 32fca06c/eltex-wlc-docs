
```shell
wlc
  ap-profile default-ap
    description "default-ap"
    password ascii-text encrypted 8CB5107EA7005AFF
  exit
exit
```

```shell
wlc
  airtune-profile default_airtune
    description "default_airtune"
  exit
exit
```

```shell
wlc
  radius-profile default-radius
    description "proxy"
    auth-address %ip_wlc%
    auth-password ascii-text encrypted 8CB5107EA7005AFF
    domain default
  exit
exit
```

```shell
wlc
  ssid-profile default-ssid
    description "default-ssid"
    ssid "default-ssid"
    radius-profile default-radius
    vlan-id %vlan_id%
    security-mode WPA2_1X
    802.11kv
    band 2g
    band 5g
    enable
  exit
exit
```

```shell
wlc
  ap-location default-location
    description "default-location"
    mode tunnel
    ap-profile default-ap
    airtune-profile default_airtune
    ssid-profile default-ssid
  exit
exit
```

```shell
wlc
  ip-pool default-ip-pool
    description "default-ip-pool"
    ap-location default-location
  exit
exit
```
