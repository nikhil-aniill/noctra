+++
title = "Welcome to noctra"
date = 2026-06-14T10:00:00Z
draft = false
description = "First post — a working demo of the Congo setup: featured image, syntax highlighting, and native YouTube/Vimeo embeds."
summary = "Kicking off the blog and smoke-testing the Congo theme: images, code highlighting, and native video embeds all render."
featureAlt = "Placeholder featured image showing the noctra wordmark on a dark background"
coverCaption = "Placeholder featured image — replace `featured.jpg` in this post's folder."
tags = ["meta", "hugo", "congo"]
categories = ["notes"]
+++

{{< lead >}}
First post. It exists to prove the toolchain end-to-end — Hugo Extended + Congo, dark mode, page-bundle images, syntax highlighting, and native video embeds.
{{< /lead >}}

This blog runs on the [Hugo](https://gohugo.io) static site generator with the [Congo](https://github.com/jpanther/congo) theme. Everything below is placeholder content you can delete once you've confirmed it renders.

## Images

This post is a *page bundle* (a folder with an `index.md`), so any image dropped beside it is processed by Hugo and lazy-loaded by Congo. Here's the inline placeholder:

![Placeholder network diagram on a dark background](diagram.png "A placeholder diagram resource from this page bundle")

The cover image at the top of the article is the `featured.jpg` file in this same folder — Congo detects any image whose name contains `feature` automatically.

## Syntax highlighting

A quick host sweep in **Bash**:

```bash
#!/usr/bin/env bash
# Ping-sweep a /24 and print live hosts
subnet="192.168.1"
for host in $(seq 1 254); do
  ip="${subnet}.${host}"
  (ping -c1 -W1 "$ip" &>/dev/null && echo "[+] up: $ip") &
done
wait
```

The same idea — hashing a file in **Python**:

```python
import hashlib
from pathlib import Path


def sha256(path: str, chunk: int = 8192) -> str:
    h = hashlib.sha256()
    with Path(path).open("rb") as f:
        for block in iter(lambda: f.read(chunk), b""):
            h.update(block)
    return h.hexdigest()


if __name__ == "__main__":
    print(sha256("/etc/hostname"))
```

{{< alert >}}
These snippets are illustrative placeholders. Only run security tooling against systems you are explicitly authorised to test.
{{< /alert >}}

## Video embeds

Congo uses Hugo's built-in shortcodes for video — no large files committed to the repo. **YouTube** needs only the video ID:

{{< youtube ZJthWmvUzzc >}}

And **Vimeo** likewise:

{{< vimeo 48912912 >}}

That's the whole smoke test. Edit or delete this post, then write your own.
