# Hotwire Native — Claude Code Skill

A Claude Code Agent Skill for Rails developers building iOS/Android apps with
[Hotwire Native](https://native.hotwired.dev).

**Unique value:** verified real-world gotchas from actual builds — the API deltas, Swift 6
quirks, and Rails/Propshaft traps that the official docs don't cover. Not a docs mirror.

**Verified against:** hotwire-native-ios 1.2.2 · hotwire-native-android 1.2.8 (docs-sourced) · Rails 8.1

---

## What it covers

- iOS and Android project setup (UIKit lifecycle, Gradle, ATS)
- Path configuration — JSON anatomy, ordering rules, server-deployed behavior changes
- Rails integration — `hotwire_native_app?`, hiding web chrome, persistent auth, CSRF rules
- Navigation — tab bars, modal vs push, snapshot cache
- Native screens — SwiftUI via `UIHostingController`, Jetpack Compose via `HotwireFragment`
- Bridge components — JS ↔ Swift/Kotlin message protocol, progressive enhancement
- Push notifications — APNs/FCM, Noticed gem, token idempotency
- Deployment — TestFlight, Play Internal Testing, device URL switching
- Troubleshooting — symptom → cause table, debugging order for "native thing doesn't show"

---

## Install

### Claude Code plugin marketplace (recommended)

```
/plugin install hotwire-native
```

Or browse via `/plugin > Discover` in Claude Code.

### Manual — copy to `~/.claude/skills/`

```bash
git clone https://github.com/cuongnc0211/hotwire-native-skill.git
cp -r hotwire-native-skill/skills/hotwire-native ~/.claude/skills/hotwire-native
```

### Per-project symlink

```bash
mkdir -p .claude/skills
ln -s /path/to/hotwire-native-skill/skills/hotwire-native .claude/skills/hotwire-native
```

---

## How it works

Claude loads `SKILL.md` first on activation. `SKILL.md` contains the decision framework,
fast-path checklist, routing table, and top gotchas. Claude then loads individual files
from `references/` on demand as the question narrows.

```
skills/hotwire-native/
├── SKILL.md             # entry point — decision framework, routing table, top gotchas
└── references/          # 13 task-focused files loaded on demand
    ├── rails-integration.md
    ├── path-configuration.md
    ├── setup-ios.md
    ├── setup-android.md
    ├── navigation-and-tabs.md
    ├── native-screens-ios.md
    ├── native-screens-android.md
    ├── bridge-components.md
    ├── bridge-components-ios.md
    ├── bridge-components-android.md
    ├── push-notifications.md
    ├── deployment.md
    └── troubleshooting.md
```

---

## Re-verification

Content marked `✅ Verified (hotwire-native-ios x.y.z, Rails x.y)` was confirmed in a
real build. Unmarked content is docs-sourced. When a new SDK version ships, re-check:

```bash
# Confirm iOS SDK signatures in your Xcode DerivedData
find ~/Library/Developer/Xcode/DerivedData -path "*SourcePackages/checkouts/hotwire-native-ios*"
grep -rn "public func\|public init\|public var" <that-path>/Source
```

Update the verified-versions statement in `SKILL.md` and the `✅` markers in affected
reference files after re-verification.

---

## Further reading

- [Hotwire Native official docs](https://native.hotwired.dev)
- [hotwire-native-ios on GitHub](https://github.com/hotwired/hotwire-native-ios)
- [hotwire-native-android on GitHub](https://github.com/hotwired/hotwire-native-android)
- *Hotwire Native for Rails Developers* by Joe Masilotti (PragProg) — recommended book

---

## License

MIT — see [LICENSE](LICENSE).
