# Spotycast

Spotycast is a Docker-based audio bridge that exposes Spotify playback as a standard HTTP/Icecast stream on your local network.

It is designed for mixed audio setups where you want to reuse a single playback chain (DAC/amp/speakers) across systems like Roon and LMS/Lyrion, without adding extra dedicated Spotify hardware.

Website / docs: https://spotycast.ovh

## What problem does this solve?

Spotify is often isolated from existing “audiophile” or self-hosted playback stacks. If your main system is Roon, LMS/Lyrion, or a network player that can read HTTP radio streams, integrating Spotify can mean:
- adding another Spotify Connect device
- switching inputs on the DAC/amp
- relying on brittle integrations that can break when upstream behavior changes

Spotycast treats Spotify as an external source and makes it consumable by any client that can play a standard HTTP stream.

## How it works (high level)

- A Spotify endpoint runs inside an isolated Docker environment.
- Audio output is captured and published as a clean HTTP/Icecast stream.
- Your existing player (Roon, LMS/Lyrion, network players, etc.) consumes that stream like any other “web radio” source.

This keeps the rest of your playback chain unchanged.

## Typical use cases

- Reuse one DAC for Spotify and other sources
- Add Spotify playback to Roon or LMS/Lyrion as a standard network stream
- Avoid extra Spotify Connect hardware devices
- Keep a predictable playback path in mixed setups

## Audio quality and expectations

Audio quality depends on the playback path used.

- Open Spotify Connect implementations are typically limited to Spotify’s “Very High” quality (often up to ~320 kbps).
- An optional setup can expose the stream as FLAC over HTTP. When Spotify’s lossless tier is available for the account/region and enabled, this is intended to avoid unnecessary transcoding at the bridge level.

This is not a blanket claim that playback is always lossless; availability depends on Spotify and client behavior.

## Editions

- **Free**: standard installation, stable MP3/AAC stream (lossy).
- **Premium**: additional convenience features, FLAC streaming support, update/rollback support.

## FAQ

### Can Spotify be used with Roon?
Spotify is not natively supported by Roon. Spotycast exposes Spotify playback as a standard HTTP stream that Roon can consume as a network audio source.

### Is this a replacement for Spotify Connect?
No. Spotycast uses Spotify playback and exposes the audio externally rather than replacing Spotify Connect.

### Is this a public broadcast?
No. Spotycast is designed for local playback within a private network (LAN). It is not intended for public redistribution.

## Support

- Issues: https://github.com/chourmovs/spotycast/issues
- Website / documentation: https://spotycast.ovh

## License

Choose a license and add it as `LICENSE` (MIT is usually a good default for permissive distribution).
