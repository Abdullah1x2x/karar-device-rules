# karar-device-rules

Device rules for the [karar-ai](https://github.com/Abdullah1x2x/karar-ai) app: which GGUF models to suggest for each device tier.

The app fetches `rules.<platform>.v2.json` from:

```
https://cdn.jsdelivr.net/gh/Abdullah1x2x/karar-device-rules@main/rules.<platform>.v2.json
```

If the fetch fails, the app falls back to the copy bundled in `src/store/bundledDeviceRules`.

## Updating

1. Edit `rules.android.v2.json` or `rules.ios.v2.json`. Keep `schema_version` at major `2`.
2. Bump `rules_version` (format `YYYY-MM-DD.N`).
3. Push to `main`. jsDelivr caches `@main` for up to 12 hours; purge it at `https://purge.jsdelivr.net/gh/Abdullah1x2x/karar-device-rules@main/rules.android.v2.json` to update sooner.

Initial content is derived from the MIT-licensed bundled rules of PocketPal AI.
