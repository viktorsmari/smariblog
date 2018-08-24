---
title: "Setting post language using franc and frontmatter"
date: 2015-11-05
author: Smári McCarthy
language: en
tags: ["Programming", "Bash"]
---

This was handy:

```bash
for a in *.md; do
    lang=$(cat $a | franc);
    if [ "$lang" = "eng" ]; then
        frontmatter set $a language en
    else
        frontmatter set $a language is
    fi
done;
```
