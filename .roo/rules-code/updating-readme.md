---
description: |
  This document provides guidelines for updating the `README.md` file in the repository.
  The `README.md` is generated from the `README.md.gotmpl` and `values.yaml` files.
  It is important to follow the steps below to ensure that the documentation remains consistent and up-to-date.
globs: charts/*/README.md
alwaysApply: true
---


### Editing `README.md` file

1. The `README.md` file is generated from the `README.md.gotmpl` and `values.yaml` files and should not be edited directly.
2. If you need to add or modify a value in the `README.md`, edit the corresponding entry in `values.yaml` and then regenerate the documentation.
   - Run `pre-commit run -a` to regenerate the documentation after making changes to `values.yaml`.
3. If you need to add a new section to the `README.md`, you can do so by editing the `README.md.gotmpl` file.
   - Run `pre-commit run -a` to regenerate the documentation after making changes to `README.md.gotmpl`.
