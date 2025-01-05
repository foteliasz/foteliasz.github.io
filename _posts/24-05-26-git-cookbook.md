---
title: Git cookbook
date: 2024-05-23
categories: [Cookbook]
tags: [git, cookbook]
author: foteliasz
---

## Git clone remote repo at specific branch

```bash
git clone --branch <branch_name> <remote_address> <local_path>
```

Examples ↓

```bash
git clone \
    --branch "3.10" \
    https://github.com/python/cpython.git \
    ~/sources/external/python/cpython
```
