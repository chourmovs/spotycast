# Spotycast — Spotify to Icecast Bridge (Roon, LMS, Volumio)

Spotycast turns Spotify playback into a stable HTTP / Icecast stream that can be consumed by Roon, LMS (Lyrion), Volumio and any network audio player supporting radio URLs.

It restores a missing layer in many audio stacks: a reliable, reusable **radio-style endpoint** for Spotify.

---

## Spotify Lossless with Roon

Spotify is introducing higher-quality playback and Exclusive Mode (bit-perfect on Windows).

However, **Spotify still does not integrate with Roon natively**.

➡️ Full breakdown:  
https://spotycast.ovh/spotify-lossless-roon/

In practice:

- You **cannot use Spotify Lossless directly inside Roon**
- Spotycast provides a **workaround via HTTP streaming**
- This introduces a republishing layer (not strictly bit-perfect)
- But enables **stable integration across your audio system**

---

## What Spotycast does

Spotycast republishes Spotify playback as a standard HTTP stream:

```
Spotify → PulseAudio → Liquidsoap → Icecast → Player (Roon / LMS / Volumio)
```

Instead of relying on native Spotify support on every device, you expose a single **radio endpoint URL** usable everywhere.

---

## Use cases

- Spotify with Roon  
  https://spotycast.ovh/spotify-with-roon/

- Spotify to Icecast bridge  
  https://spotycast.ovh/spotify-to-icecast/

- Installation guide (Docker / Debian)  
  https://spotycast.ovh/how-to-install/

- Architecture and pipeline  
  https://spotycast.ovh/how-it-works/

---

## Why this approach matters

In many real-world setups, the weakest point is not the DAC or the renderer — it's the lack of a stable source.

Spotycast solves this by:

- creating a **consistent HTTP stream**
- decoupling Spotify from playback devices
- enabling compatibility with legacy or mixed systems
- providing a **single URL your entire stack can consume**

---

## Limitations

Spotycast is intentionally not a "bit-perfect" solution.

- Audio is **republished through Liquidsoap**
- Not a native Spotify integration in Roon
- Depends on Spotify playback behavior
- Introduces buffering (HTTP streaming latency)

This is a trade-off:

➡️ You lose strict bit-perfect playback  
➡️ You gain a **stable, network-wide audio endpoint**

---

## Free vs Premium

Spotycast supports two modes:

### Free (Spotify Connect path)
- Stable and simple
- Up to Spotify's standard quality (~320 kbps)

### Premium (advanced path)
- FLAC / lossless-oriented workflow (where available)
- Additional automation and control features

More details:  
https://spotycast.ovh/version-premium/

---

## Quick start

Deploy the container (example):

```bash
docker compose up -d
```

Then inside the container:

```bash
cd /root/binaries
./spotifyd-free
```

Open Icecast:

```
http://<HOST>:28000
```

Copy a mountpoint and add it as a radio stream in your player.

---

## When should you use Spotycast?

Spotycast is useful if:

- You use Roon but want Spotify as a source
- Your devices don't support Spotify natively
- You want a **stable LAN endpoint**
- You prefer a **radio-style architecture**

---

## When you should NOT use it

- If you need strict bit-perfect playback to a DAC
- If you only listen from a single desktop device
- If native Spotify apps already meet your needs

---

## Related resources

- Spotify Lossless with Roon  
  https://spotycast.ovh/spotify-lossless-roon/

- Spotify to Icecast  
  https://spotycast.ovh/spotify-to-icecast/

- How it works  
  https://spotycast.ovh/how-it-works/

- FAQ  
  https://spotycast.ovh/faq/

---

## License

See repository license.
