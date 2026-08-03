#!/usr/bin/env bash
set -euo pipefail

project_root="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"
export UV_PROJECT_ENVIRONMENT="$project_root/.venv.nosync"

template_dir="$project_root/nbconvert_templates"
nb="$1"
pdf="${nb%.ipynb}.pdf"

uv run jupyter nbconvert --to webpdf "$nb" \
    --template compactlab \
    --TemplateExporter.extra_template_basedirs="$template_dir"

# open "$pdf"
