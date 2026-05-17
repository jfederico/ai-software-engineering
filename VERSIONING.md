# Versioning Policy

This project uses Semantic Versioning for methodology releases.

## Version Format

MAJOR.MINOR.PATCH

- MAJOR: breaking structural changes to methodology flow or required artifacts
- MINOR: backward-compatible additions (new templates, prompts, sections)
- PATCH: clarifications, typo fixes, non-breaking wording improvements

## What Counts as Breaking

Examples:
- Changing required phase order
- Changing required gate semantics
- Removing required output artifacts
- Renaming core files relied on by documented workflows

## Release Cadence

- Patch: as needed
- Minor: when meaningful improvements accumulate
- Major: rare, only for deliberate framework evolution

## Changelog Requirement

Every user-visible change must be reflected in CHANGELOG.md.
