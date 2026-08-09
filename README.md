# MMD HUD iframe Release

Public compiled test artifacts for the private Dragon Raja iframe Theme.

- `host/mmd-hud-iframe-host.js`: Host IIFE injected into MMD.
- `frame/mmd-hud-iframe-frame.js`: Frame IIFE loaded by the Host into a sandboxed `srcdoc` iframe.
- Vue SFC CSS is bundled into the Frame IIFE; no separate Frame stylesheet is required.
- Dragon Raja Vue / TypeScript source code is not published in this repository.

Build ID: `dragon-raja-458456cb491f`

Private source commit: `458456cb491f1b233f1feccf3c248785f998ccef`

Protocol: `2`

Theme: `dragon-raja`

Host and Frame in each release commit are produced from the same private source commit. Always load both files from one immutable public commit SHA; never mix artifacts from different commits.

## MMD Dragon Raja injection

Replace `<release-full-sha>` with the immutable full SHA of this public artifact release:

```html
<script>
(() => {
  const RELEASE_BASE =
    'https://cdn.jsdelivr.net/gh/Godcount10/mmd-hud-iframe-release@<release-full-sha>';

  if (window.__MMD_HUD_IFRAME__) {
    window.__MMD_HUD_IFRAME__.destroy();
  }

  window.__MMD_HUD_IFRAME_CONFIG__ = {
    frameScriptUrl: `${RELEASE_BASE}/frame/mmd-hud-iframe-frame.js`,
    theme: 'dragon-raja',
  };

  const hostScript = document.createElement('script');
  hostScript.src = `${RELEASE_BASE}/host/mmd-hud-iframe-host.js`;
  hostScript.async = true;
  (document.head || document.documentElement).appendChild(hostScript);
})();
</script>
```

Rollback Host and Frame together to public commit `28b41f72e27bf974284dd7eb339d815612d5b62e` if needed.
