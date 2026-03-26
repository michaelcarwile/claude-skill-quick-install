# Changelog

All notable changes to claude-skill-quick-install.

## [Unreleased]

- **fix**: Swap `marketplace.json` for `plugin.json` as primary metadata source — handles repos without marketplace manifest
- **feat**: Add standalone skill detection — repos with `skills/*/SKILL.md` but no `.claude-plugin/` install via file copy
- **docs**: Update README with git clone as primary install method, updated How It Works and Requirements

## 2026-03-23

- **refactor**: Convert from plugin to standalone skill — remove `.claude-plugin/` manifests and command file, keep only `skills/quick-install/SKILL.md` (`07b0e4b`)

## 2026-03-14

- **fix**: Use `curl` instead of `gh` for fetching marketplace manifest — works without GitHub CLI for public repos (`c8a7dc7`)
- **docs**: Add README with install instructions and usage examples (`7d722b0`)
- **feat**: Initial quick-install plugin — local marketplace approach, `curl`/`gh` fallback chain, one-command install (`e593584`)
