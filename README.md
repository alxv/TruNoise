# TruNoise

**Seamless sleep noise for iPhone** — procedural pink, brown, and Pro color noise with no loop seams, no ads, and no subscription.

TruNoise is built for reliability at 3 AM: continuous background playback, alarm-friendly fade-outs, widgets, and a generous free tier. Pro is a **one-time** unlock.

## Highlights

- **No audible loop seams** — procedural generation, not looping audio files
- **Free forever** — pink & brown noise, free blends, overnight playlists, 1 saved mix, sleep timer, widgets
- **Alarm-friendly** — fades out smoothly when the Clock alarm rings (does not auto-resume under your alarm)
- **Zero ads**
- **TruNoise Pro** (one-time IAP) — 90 curated sounds, blue & violet, unlimited saves, overnight Pro playlists, 10-band EQ, Shortcuts/Siri, optional binaural underlay

TruNoise does not provide medical advice. Binaural tones are for relaxation only.

## Requirements

- iOS (see Xcode project deployment target)
- Xcode 16+ recommended
- Apple Developer account for device / App Store builds

## Project layout

| Path | Purpose |
|------|---------|
| `TruNoise/` | Main app (SwiftUI, audio engine, StoreKit, intents) |
| `TruNoiseWidgets/` | Home Screen / Lock Screen widgets |
| `TruNoiseShared/` | App Group bridge between app and widgets |
| `TruNoiseTests/` | Unit tests |
| `AppStore/` | App Store Connect copy & setup guide |
| `QA/ReleaseChecklist.md` | Manual release QA |
| `Privacy.md` | Privacy policy (host at your Privacy Policy URL) |

## Build & run

1. Open `TruNoise.xcodeproj` in Xcode.
2. Select the **TruNoise** shared scheme.
3. For local IAP testing: **Edit Scheme → Run → Options → StoreKit Configuration** → `TruNoise/Products.storekit`.
4. Run on a Simulator or device.

```bash
xcodebuild -scheme TruNoise -destination 'platform=iOS Simulator,name=iPhone 17' test
```

## Free vs Pro

| | Free | Pro (`com.trunoise.app.pro`) |
|--|------|------------------------------|
| Colors | Pink, brown | + White, green, blue, violet |
| Sounds | Free essentials | 90 curated Pro sounds |
| Saved mixes | 1 (pink/brown) | Unlimited |
| Sleep timer | Up to 2 hours | Overnight lengths (3–10 hr) |
| EQ / binaural / Pro playlists | — | Included |

## Identifiers

| Item | Value |
|------|--------|
| Bundle ID | `com.trunoise.app` |
| Widgets | `com.trunoise.app.widgets` |
| App Group | `group.com.trunoise.app` |
| URL scheme | `trunoise://` |
| Pro IAP | `com.trunoise.app.pro` (non-consumable) |

## App Store

- Metadata & ASO: [`AppStore/AppStoreCopy.md`](AppStore/AppStoreCopy.md)
- Connect setup: [`AppStore/AppStoreConnectSetup.md`](AppStore/AppStoreConnectSetup.md)
- Privacy policy: [`Privacy.md`](Privacy.md) → publish at `https://trunoise.app/privacy`
- Support: `https://trunoise.app/support`

## Privacy

TruNoise does **not** track you, show ads, or sell personal data. Playback preferences and mixes stay on-device (and in the App Group for widgets). Purchases are handled by Apple. See [`Privacy.md`](Privacy.md).

## License

Proprietary — all rights reserved unless otherwise stated by the copyright holder.
