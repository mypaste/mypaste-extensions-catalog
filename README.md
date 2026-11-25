# mypaste-extensions-catalog

Published marketplace feed for 34 MyPaste extensions.

This repository is an independent copy of the tracked `dist/` files from the former `mypaste-code-extensions` monorepo at commit `2af6675ab1473c9e38146ea0b6da68256a293440`. Every `.mypaste-plugin` archive, SHA-256 checksum, and the deterministic `index.json` feed is preserved byte-for-byte.

Feed URL for MyPaste:

```text
https://raw.githubusercontent.com/mypaste/mypaste-extensions-catalog/main/index.json
```

Package sources are in the sibling repositories named after their plugin IDs under <https://github.com/mypaste>.

## Publishing

Each entry in `index.json` is validated by the host that reads it. Two limits
bite first: `name` may be at most 72 characters and `description` at most 280
(`MaxNameRunes` / `MaxDescription` in the host's `internal/extension`). A host
that cannot read an entry skips it rather than failing the whole feed, so an
over-long description does not break the marketplace — it makes that one
package disappear from it. `sha256` is the digest of the archive beside it.


## License

MIT. See [LICENSE](LICENSE).
