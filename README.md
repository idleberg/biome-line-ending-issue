# Biome Issue

## Description

I have noticed the following behaviour when running Biome on different operating systems:

- the default `lineEnding` on Windows is CRLF
- the default `lineEnding` on other operating systems is LF

This in itself is a sensible default. However, I was expecting that this can be overridden
using a config file. Likewise, I was expecting the setting specified in `.editorconfig` to
be respected, i.e. `end_of_line = lf`.

### What I'm seeing

First run

1. Running `biome check --line-ending=lf` expects CRLF on Windows
2. Running `biome check --line-ending=lf` expects LF on other operating systems

Second run

1. Running `biome check --use-editorconfig=true` expects CRLF on Windows
2. Running `biome check --use-editorconfig=true` expects LF on other operating systems

### What I'm expecting

1. Specifying neither, `lineEnding` or `end_of_line = lf`, should default to CRLF on Windows
2. Specifying neither, `lineEnding` or `end_of_line = lf`, should default to LF on other operating systems
3. Specifying either, `lineEnding` or `end_of_line = lf`, should follow that setting
