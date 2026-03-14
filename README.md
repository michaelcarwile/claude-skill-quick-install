# quick-install

Install Claude Code plugins directly from a GitHub repo in one command.

## The Problem

Installing a Claude Code plugin from GitHub requires two commands:

```
/plugin marketplace add owner/repo
/plugin install plugin-name@owner-repo
```

You need to know the marketplace naming convention and the plugin name inside the repo. This plugin reduces it to:

```
/quick-install owner/repo
```

## Install

```
/plugin marketplace add diffyweb/claude-plugins
/plugin install quick-install@diffyweb-claude-plugins
```

## Usage

```
/quick-install owner/repo
/quick-install https://github.com/owner/repo
```

The command fetches the plugin's marketplace manifest from GitHub, adds the repo as a marketplace, and installs the plugin — all in one step.

## How It Works

1. Parses the GitHub `owner/repo` from the input
2. Fetches `.claude-plugin/marketplace.json` via `gh api` to get plugin name(s)
3. Runs `claude plugin marketplace add owner/repo`
4. Runs `claude plugin install plugin-name@derived-marketplace-name`
5. Prompts you to `/reload-plugins`

## Requirements

- [GitHub CLI](https://cli.github.com/) (`gh`) installed and authenticated
- The target repo must have a `.claude-plugin/marketplace.json`
