---
title: Hugo syntax highlighting
date: 2015-11-05
tags: ["Hugo"]
---

Hugo's syntax highlighting method is annoying. Instead of using the Markdown pretty-much-standard 
method:

    ```language
    code
    ```

You have to use weird template shortcodes:

    { {< highlight language >}}
    code
    { {< /highlight >}}

(With fewer spaces -- can't figure out how to escape shortcodes either!)

Perhaps this can be changed...
