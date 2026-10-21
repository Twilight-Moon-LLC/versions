# versions

Publishes the current version of each Twilight Moon resource, so a running server can tell when it is out of date.

`twilightmoon.json` is read by every `tm_*` resource at start, through `tm.version.check` (see `tm_lib/docs/utils/version.md`). It must stay in a public repo, because the check downloads the raw file.

Each entry has two fields:

```json
{ "tm_lib": { "version": "0.4.0", "security": "0.4.0" } }
```

- `version`: the newest release.
- `security`: the oldest release with no known security problem. Installs below it log an error.

`packages/boilerplate/new-resource.ps1` adds a new resource at `0.1.0`. Update the entry whenever a release is cut, and commit it in this repo.
