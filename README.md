# OpenSprinkler

## Overview

Simple OpenSprinkler / Homebridge integration.

### What works:

- Read and set rain delay
- Automatically update changes in state
- Show sprinkler state: idle, scheduled, running
- Show remaining duration
- Turn off sprinklers
- Ad-hoc turn on a single valve at a time.
- Allow duration to be specified per-station when enabled

### What doesn't work:

- Starting multiple programs in sequence (turning on multiple stations causes them to run concurrently)
- Persisting Home-configured station-specific default durations after restart
- Does not support multiple OpenSprinkler systems

## Configuration

- `host`: The IP or DNS name of the OpenSprinkler controller
- `password`: Either the md5 hash of the password, or the password in plain text. I.E. `{"md5": "a6d82bced638de3def1e9bbb4983225c"}` or `{"plain": "opendoor"}`
- `enabledStationIds`: The stationIds you wish to have registered.
- `defaultDurationSecs`: The duration for which a station will be run when toggled on.
- `pollIntervalMs`: The interval at which homebridge-opensprinkler will poll for state changes in OpenSprinkler.

Sample configuration:

```
{
  "platform": "OpenSprinkler",
  "host": "sprinkler.lan",
  "password": {"md5": "a6d82bced638de3def1e9bbb4983225c"},
  "enabledStationIds": [0, 1, 2, 3],
  "defaultDurationSecs": 600,
  "pollIntervalMs": 5000
}
```

