# Maestro IR catalog

Public IR code catalog for [Maestro](https://github.com/BMac1203/maestro) (open universal-remote hub).
Derived from the MIT-licensed [Flipper-IRDB](https://github.com/Lucaslhm/Flipper-IRDB), rendered to
Maestro codesets by `tools/build_catalog.py` in the Maestro repo.

- `index.json` — Brand → Type → Model list (the exact-model picker), all AV models.
- `codes/<id>.json` — pre-rendered codeset for one model: `{b,m,t,btns:[{n,f,r[]}]}` (raw µs timings).
- `codes_available.json` — ids that have a rendered codeset.

The hub never fetches this directly; the app pulls a model's codes and POSTs them to the hub
(`/api/device/import`), keeping the hub LAN-only.
