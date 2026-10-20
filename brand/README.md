# Charcoal brand and icon system

One family, two products:

- **Charcoal APK** — green accent (`#3DDC84`), circle center, four ticks
- **Charcoal IPA** — amber accent (`#F0B35B`), rounded-square center, three ticks

Both share the same charcoal tile, ring geometry, corner radius, and spacing.

## Files

| Pattern | Purpose |
| --- | --- |
| `apk-primary.svg` / `ipa-primary.svg` | 1024 app icon source |
| `apk-small.svg` / `ipa-small.svg` | 16–48 optimized geometry |
| `apk-tray.svg` / `ipa-tray.svg` | monochrome template tray icon |
| `apk-social.svg` / `ipa-social.svg` | social avatar source |
| `apk-dmg.svg` / `ipa-dmg.svg` | DMG volume icon source |
| `ipa-mark.svg` | transparent mark for Icon Composer |
| `wordmark-*-light.svg` / `wordmark-*-dark.svg` | horizontal lockups |
| `ui-*.svg` | shared 24px line icons |

## Rules

- Keep the tile, ring, and center aligned to the 1024 grid used by the sources.
- Green is APK only; amber is IPA only. Do not introduce a third accent.
- The tray variants must stay black with alpha and no background tile.
- Do not put text inside the app icons; text belongs to the wordmarks.
- Small sizes use the `*-small` geometry, not the primary scaled down.
