# forge-ci.github.io

The forge-ci organization's GitHub Pages site.

## `soldr-redirect.v1.json`

The toolchain redirect manifest. soldr and setup-soldr fetch it first to
learn where the toolchain catalogue lives. `toolchain.origins` lists the
catalogue origins in order of preference; clients try them in that order
and use the next one when an origin fails. To move the catalogue, edit this
file. Released clients follow the change, so you don't need to ship a new
soldr.

Clients keep the last copy they fetched, and they also carry a built-in
fallback list, so a bad edit or an outage here doesn't strand them. Keep
`schema_version` at 1 unless the format changes in a way old clients can't
read.

## `soldr-toolchain/`

A verbatim mirror of https://zackees.github.io/soldr-toolchain. Don't edit
it by hand. The `publish-multipart` workflow in zackees/soldr-toolchain
replaces it after every Pages deploy, pushing with a deploy key.
