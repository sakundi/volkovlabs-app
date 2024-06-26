# RSS/Atom Data Source for Grafana

![Dashboard](https://raw.githubusercontent.com/VolkovLabs/volkovlabs-rss-datasource/main/src/img/dashboard.png)

[![Grafana 9](https://img.shields.io/badge/Grafana-9.2.2-orange)](https://www.grafana.com)
[![YouTube](https://img.shields.io/badge/YouTube-Playlist-red)](https://www.youtube.com/playlist?list=PLPow72ygztmSGfvGdXriFE-LVuS4Glg7w)
![CI](https://github.com/volkovlabs/volkovlabs-rss-datasource/workflows/CI/badge.svg)
[![codecov](https://codecov.io/gh/VolkovLabs/volkovlabs-rss-datasource/branch/main/graph/badge.svg?token=2W9VR0PG5N)](https://codecov.io/gh/VolkovLabs/volkovlabs-rss-datasource)
[![CodeQL](https://github.com/VolkovLabs/volkovlabs-rss-datasource/actions/workflows/codeql-analysis.yml/badge.svg)](https://github.com/VolkovLabs/volkovlabs-rss-datasource/actions/workflows/codeql-analysis.yml)

## Introduction

The RSS/Atom data source is a plugin for Grafana that retrieves RSS/Atom feeds and allows to visualize them using Dynamic Text and other panels.

[![RSS/Atom Data Source for Grafana | News feed tutorial for Grafana Dashboard](https://raw.githubusercontent.com/volkovlabs/volkovlabs-rss-datasource/main/img/video.png)](https://youtu.be/RAxqS2hpWkg)

### Requirements

- **Grafana 8.5+**, **Grafana 9.0+** is required for version 2.X.
- **Grafana 8.0+** is required for version 1.X.

## Getting Started

RSS/Atom data source can be installed from the [Grafana Catalog](https://grafana.com/grafana/plugins/volkovlabs-rss-datasource/) or use the `grafana-cli` tool to install from the command line:

```bash
grafana-cli plugins install volkovlabs-rss-datasource
```

## Features

- Supports RSS 2.0, RSS 1.0 and Atom.
- Works great with Dynamic Text panel by Marcus Olsson (marcusolsson-dynamictext-panel).
- Returns Channel (Feed) data, Items (Entries) or both as separate data frames.
- Extract and parse as additional fields:
  - Image from Meta.
  - H4 and Image from the Encoded content.
  - Media:Group for YouTube.
- Filter items/entries based on the selected Time Range.

## Provisioning

Grafana supports managing data sources by adding one or more YAML config files in the `provisioning/datasources` folder.

Example of provisioning the RSS/Atom Data Source for Bitcoin news feed.

```yaml
datasources:
  - name: Bitcoin
    type: volkovlabs-rss-datasource
    access: proxy
    orgId: 1
    uid: rZAdZdf7k
    version: 1
    editable: true
    jsonData:
      feed: https://news.bitcoin.com/feed/
```

## Disable Sanitize HTML

To display HTML returned from feeds please disable sanitize HTML parameter. For Docker:

```bash
GF_PANELS_DISABLE_SANITIZE_HTML=true
```

## Feedback

We love to hear from users, developers, and the whole community interested in this plugin. These are various ways to get in touch with us:

- Ask a question, request a new feature, and file a bug with [GitHub issues](https://github.com/volkovlabs/volkovlabs-rss-datasource/issues/new/choose).
- Sponsor our open-source plugins for Grafana with [GitHub Sponsor](https://github.com/sponsors/VolkovLabs).
- Star the repository to show your support.

## License

- Apache License Version 2.0, see [LICENSE](https://github.com/volkovlabs/volkovlabs-rss-datasource/blob/main/LICENSE).
