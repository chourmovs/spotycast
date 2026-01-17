# Spotycast

A pragmatic, container-first bridge to use Spotify as a standard network source (HTTP/Icecast), so you can keep a single DAC / playback chain across systems like Roon or LMS/Lyrion.

This repository is intentionally lightweight and serves as the public entry point.

## Documentation & installation

All docs and the ready-to-run setup are hosted here:
**https://spotycast.duckdns.org**

## What it does (high level)

- Exposes a **Spotify Connect** endpoint in a Docker container
- Publishes audio as a standard **Icecast / HTTP stream**
- Lets any client that supports HTTP streams consume it as a normal network source

## Why this exists

Spotify integrations outside the official ecosystem can be fragile (auth changes, Connect regressions). This project focuses on a reproducible, external bridge that keeps the playback chain stable without patching your player stack.

## Support / discussion

If you have	ps questions or want to share your setup, please use the community threads (linked on the website).

## License

See [LICENSE](LICENSE).

