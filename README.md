# PUBLIC — Claritano Growth Content

**PUBLIC REPOSITORY. DO NOT EDIT MANUALLY.**

This repository contains only final media that social platforms must retrieve
through a public HTTPS URL. Captions, queues, source files, secrets and
automation code do not belong here.

The private `studio-social-engine` writes files here immediately before
publication. Instagram reads them from:

```text
https://raw.githubusercontent.com/claritano/studio-social-content-PUBLIC/main/img/<slug>.jpg
https://raw.githubusercontent.com/claritano/studio-social-content-PUBLIC/main/reels/<slug>.mp4
```

Deleting a file here does not delete the corresponding social post.
