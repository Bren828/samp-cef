# CEF 150 client smoke test

This fixture checks the existing client behavior against the CEF 150 runtime:

- local `sampcef` asset loading and HTTP fetches;
- browser/renderer JS IPC (`cef.on`, `cef.emit`, `cef.set_focus`);
- software OSR animation, keyboard and mouse input;
- VP9 + Opus playback and expected H.264 + AAC unavailability.

Copy `index.html`, Chromium's `bear-vp9-opus.webm`, and `bear-1280x720.mp4` renamed to `bear-h264-aac.mp4` into `<GTA>/cef/assets/cef150-smoke/`. Run `node scripts/smoke-http-server.mjs`, compile `mode.pwn` with `server/cef.inc`, and load it with the CEF server plugin or open.mp component.
