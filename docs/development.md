# Editing and rendering

## Files

- Source of truth: [diagrams/metadata-governed-deployment.puml](diagrams/metadata-governed-deployment.puml)
- Rendered artifact: [diagrams/rendered/metadata-governed-deployment.svg](diagrams/rendered/metadata-governed-deployment.svg)

## Requirements

Use native Windows AMD64 PlantUML. The diagram was rendered and visually inspected with PlantUML **1.2026.7**. It uses the bundled `<C4/C4_Container>` library and Smetana layout; no remote include is required.

From the repository root in PowerShell:

```powershell
$renderer = Join-Path $env:LOCALAPPDATA 'PlantUML-Native\plantuml.exe'
$source = Join-Path $PWD 'docs\diagrams\metadata-governed-deployment.puml'
$output = Join-Path $PWD 'docs\diagrams\rendered'
& $renderer -tsvg -o $output $source
if ($LASTEXITCODE -ne 0) { throw 'PlantUML rendering failed' }
```

Keep each `Container(...)` declaration on one physical line without explicit `\n` escapes. Keep source and rendered SVG together when changing the model. Inspect the output for clipped labels, overlapping relationships, or renderer errors before publishing.

## Scope

This is a container view, not a deployment topology or component implementation model. External systems remain outside the system boundary as in the supplied diagram. Relationship labels describe intent; network protocols and authentication mechanisms are not specified in the source diagram and have not been invented here.
