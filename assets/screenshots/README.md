# Screenshots

Drop product screenshots here, then reference them from the top of `README.md`.

Recommended set (PNG, 1600px wide, dark theme — the console is dark by default):

| File | Content |
| --- | --- |
| `live-view.png` | 4-split live view with real cameras, PTZ panel visible |
| `playback.png` | Playback timeline with a recording selected |
| `device-list.png` | Device list showing ONVIF and GB28181 devices |
| `system-info.png` | System info page (resource charts, license status) |
| `demo.gif` | 10–15 s loop: open live view, switch stream, open playback |

Reference in README above the feature table:

```markdown
![CCNVR live view](assets/screenshots/live-view.png)
```

Keep total size under ~5 MB — GitHub serves these from the repo, and large
GIFs make the README slow to load on mobile. Compress with `pngquant` or
`gifsicle -O3 --lossy=60`.
