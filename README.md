# egregia-media

Public image host for Egregia's Instagram automation. **Images only.**

## Why this repo exists

Instagram's Content Publishing API does not accept uploaded image bytes. It
only accepts a public HTTPS URL, which Meta's own servers fetch. The source
repo (`claritano/studio-marketing-pilot-egregia`) is private, so its
`raw.githubusercontent.com` URLs return 404 to Meta.

This repo is the minimum public surface needed to solve that: each JPEG is
pushed here by the workflow moments before the post goes out, and Instagram
fetches it from:

```
https://raw.githubusercontent.com/claritano/egregia-media/main/img/<slug>.jpg
```

## What is and is not here

| Here | Not here |
|---|---|
| JPEGs already published to Instagram | captions, drafts, the queue |
| this README | any code, workflow or ledger |
|  | anything unpublished |

Nothing here is secret: every image in `img/` is already visible on the public
Instagram profile.

## Do not edit by hand

Files are written by `scripts/publish_instagram.py` in the private source repo,
authenticated with the fine-grained PAT `MEDIA_REPO_TOKEN` (Contents: read and
write, scoped to this repository only). If a publish fails midway, the workflow
deletes the image it had just pushed, so orphans should not accumulate.

Deleting an image here does **not** remove the corresponding Instagram post —
Instagram keeps its own copy once published.