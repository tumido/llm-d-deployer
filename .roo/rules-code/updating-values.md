---
description: This rule ensures the structure and content of the values file will work with the schema and readme generator.
globs: charts/*/values.yaml
alwaysApply: true
---

# Editing the chart values in `values.yaml`

1. Respect the indentation and formatting of the existing `values.yaml` file.
   - Use spaces for indentation (2 spaces per level).
   - Ensure that the YAML structure is valid and follows the correct syntax.
   - Do not leave any trailing spaces or tabs.
   - Between every two entries, leave a blank line to improve readability.
   - Do not panic when you see the `values.schema.json` file is not up to date. It will be automatically updated when you run `pre-commit run -a` after making changes to `values.yaml`.
2. Always provide an annotation for each new value added to `values.yaml`.
   - Annotations should be in the format `# -- Description` and located directly above the value.
3. If you are adding a new value that is of a complex type (e.g., a map or list), ensure that you provide a clear and concise description of its purpose and usage.
4. If you are adding a new value that is of a complex type (e.g., a map or list) and the default value is not obvious, provide a meaningful schema annotation that describes the structure and expected content of the value.
   - Do not add schema annotations for simple values like strings, integers, or booleans unless they require additional context.
   - Schema annotation is located between two entries of `# @schema` above the documentation comment.
   - Schema annotation conforms to the type required by [Helm schema](https://github.com/dadav/helm-schema/) generator

   example:
   ```yaml
   # @schema
   # items:
   #   type: string
   # @schema
   # -- This value is a list of strings.
   myListOfStrings: []
   ```

5. If you are modifying an existing value, ensure that you update the annotation to reflect the new purpose or usage.
6. **Every time a change to `values.yaml` is made, make sure to run `pre-commit run -a` right after this change** to regenerate the `values.schema.json` and `README.md` files.
