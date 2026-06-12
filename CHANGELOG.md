# Changelog

## [0.2.0](https://github.com/cuongnc0211/hotwire-native-skill/compare/v0.1.0...v0.2.0) (2026-06-12)

### 🏗️ Refactor

* migrate to Claude Code plugin marketplace structure — remove `hotwire-native/` subdirectory wrapper; skill files now published via marketplace manifest

## [0.1.0](https://github.com/cuongnc0211/hotwire-native-skill/releases/tag/v0.1.0) (2026-06-11)

### 🎉 Features

* initial public release — SKILL.md decision framework, 9-step iOS fast-path checklist, routing table, 8 top gotchas, verified-versions statement
* 13 reference files in `references/`: rails-integration, path-configuration, setup-ios, setup-android, navigation-and-tabs, native-screens-ios, native-screens-android, bridge-components (shared + iOS + Android), push-notifications, deployment, troubleshooting

### 📄 Documentation

* verified against hotwire-native-ios 1.2.2 (real build — Pave-AI app), hotwire-native-android 1.2.8 (docs-sourced), Rails 8.1, Propshaft + importmap, Swift 6 / Xcode 17+
* re-verification trigger noted: when hotwire-native-ios 1.3.0 ships, re-check bridge bar-button API, Navigator init, HotwireTabBarController init
