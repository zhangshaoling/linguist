# Ku upstream Linguist submission notes

This fork branch prepares the minimal Linguist-side assets for adding Ku as a language.

## Current draft changes

- `lib/linguist/languages.yml`
  - Adds `Ku` as a programming language.
  - Extension: `.ku`.
  - Color: `#cba6f7`.
  - Ace mode: `text`.
  - Temporary highlighting scope: `none`.
  - Language ID generated with Linguist's `script/update-ids` algorithm: `84088291`.
- `samples/Ku/example.ku`
  - Representative Ku / Dao code from `zhangshaoling/ku`.
  - Source license: MIT.

## Blockers before opening an upstream PR

GitHub Linguist requires evidence of widespread public usage for new extensions:

- Normally at least 2000 indexed files for an extension expected to appear multiple times per repo.
- Reasonable distribution across unique `user/repo` combinations.
- Search evidence excluding the primary author when the owner dominates results.

Current evidence checked through GitHub Code Search:

```text
extension:ku                         -> 406 files
extension:ku -user:zhangshaoling      -> 345 files
"思 " extension:ku                    -> 27 files
"思 " extension:ku -user:zhangshaoling -> 0 files
```

This is not enough for a serious upstream PR yet.

## Grammar blocker

Linguist expects grammar additions to be performed via:

```bash
script/add-grammar <grammar-repo-url>
```

The Ku repository currently has a local grammar at:

```text
zhangshaoling/ku/syntaxes/ku.tmLanguage.json
```

Before a polished upstream PR, publish a small dedicated grammar repository or package that Linguist can add as a grammar submodule.

## Recommended next steps

1. Keep this fork branch as a draft staging area.
2. Complete `zhangshaoling/ku` README reality documentation.
3. Publish more real `.ku` examples and, ideally, separate example repositories.
4. Package the Ku TextMate grammar in a dedicated public grammar repository with an accepted license.
5. Re-check GitHub Code Search usage counts.
6. Open the upstream PR only after usage and grammar evidence are strong enough.
