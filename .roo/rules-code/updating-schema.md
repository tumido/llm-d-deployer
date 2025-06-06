---
description: This rule ensures that the JSON schema for the Helm chart values is generated whenever the `values.yaml` file is modified.
globs: charts/*/values.schema.json
alwaysApply: true
---

# Updating the JSON Schema for Helm Chart Values

**Under no circumstances edit `values.schema.json` directly or manually.**

When you modify the `values.yaml` file in a Helm chart, it is essential to regenerate the corresponding JSON schema file (`values.schema.json`) to ensure that the schema remains in sync with the values defined in `values.yaml`.

Do not edit the `values.schema.json` file directly. Instead, follow these steps:

1. **Modify the `values.yaml` file**: Make your changes to the `values.yaml` file as needed. Ensure that you follow the coding rules for editing `values.yaml`, including adding annotations and schema definitions.
2. **Regenerate the schema**: After making changes to `values.yaml`, run the following command to regenerate the `values.schema.json` file:

   ```bash
   pre-commit run -a
   ```

   This command will regenerate the schema based on the current state of `values.yaml`. It will fail initially, but it will still generate the schema correctly. To verify that the schema is generated correctly, rerun the same command one more time. If it passes without errors, the schema is correctly generated.
