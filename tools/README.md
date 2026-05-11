# Maintenance tools

This directory contains repository-maintainer checks. These tools do not change
published client artifacts.

## JS overwrite smoke contract

Run:

```bash
node tools/validate-js-overwrites.js
```

Scope:

- loads `Clash Party/ClashParty(mihomo-smart).js`,
  `Clash Party/ClashParty(mihomo).js`, and `FlClash/FlClash(mihomo).js`
  through their real `main(config)` entrypoint;
- validates alpha-3 node classification, info-node exclusion, home-node
  classification, empty-region non-fallback behavior, group order and group
  references;
- verifies subscription-native groups/rules/providers are removed;
- checks rule-provider download proxy, rule-provider references, final `MATCH`,
  TikTok target isolation, DNS fallback, TLS fingerprint handling, and the
  FlClash in-place mutation contract.

Useful options:

```bash
node tools/validate-js-overwrites.js --target smart
node tools/validate-js-overwrites.js --target normal
node tools/validate-js-overwrites.js --target flclash
node tools/validate-js-overwrites.js --json
node tools/validate-js-overwrites.js --verbose
```
