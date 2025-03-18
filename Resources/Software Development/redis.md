# Redis

- [Redis Deep Dive w/ a Ex-Meta Senior Manager](https://www.youtube.com/watch?v=fmT5nlEkl3U)

## Use cases of Redis
- Cache
- Scoring/ranking values (with sorted set)
- Rate limiter
- Geolocation DB
- Stream source
- Pub/sub broker

## Drawbacks
- Single-threaded
- Sharding is hard because everything is "key-based", so it might struggle to handle problems such as the "hot key problem"
