---
description: Treat all YAML files in the `charts/<chart-name>/templates` directory as Helm templates.
globs: charts/*/templates/**/*.yaml
alwaysApply: true
---


### Editing YAML files within `charts/<chart-name>/templates`

1. Ensure that all YAML files in the `templates` directory are valid and follow the Helm template syntax.
   - Despite the fact that the files have a YAML extension, they are actually Helm templates and should be treated as such. Do not attempt to validate them as plain YAML files.
2. Use the `helm template` command to render the templates and check for any syntax errors.
   - Run `helm template <chart-name> charts/<chart-name>` to render the templates and check for errors.
3. If you are adding a new template file, ensure that it is properly named and follows the naming conventions for Helm templates.
4. If you are modifying an existing template file, ensure that you do not break the existing functionality and that the changes are well-documented.
5. Always run `helm lint` after making changes to the templates to ensure that the chart is still valid and passes all checks.
   - Run `helm lint charts/<chart-name>` to validate the chart after making changes to the templates.
