# MMD HUD iframe Release

Public release artifacts for `mmd-hud-iframe`.

- `host/mmd-hud-iframe-host.js`: Host IIFE injected into MMD.
- `frame/mmd-hud-iframe-frame.js`: bundled Frame IIFE loaded by the Host into a sandboxed `srcdoc` iframe.
- Vue SFC CSS is injected into the Frame IIFE at build time; no separate Frame stylesheet is required.

Build ID: `dragon-raja-775a11d`
Protocol: `2`
Themes: `dragon-raja`, `bridge-debug`

Host and Frame in each commit are produced by the same build and must be loaded from the same immutable commit SHA.

## MMD Dragon Raja injection

Replace `<commit-sha>` with this release commit's immutable SHA:

```html
<script>
window.__MMD_HUD_IFRAME_CONFIG__ = {
  frameScriptUrl: 'https://cdn.jsdelivr.net/gh/Godcount10/mmd-hud-iframe-release@<commit-sha>/frame/mmd-hud-iframe-frame.js',
  theme: 'dragon-raja'
}
</script>
<script src="https://cdn.jsdelivr.net/gh/Godcount10/mmd-hud-iframe-release@<commit-sha>/host/mmd-hud-iframe-host.js"></script>
```
