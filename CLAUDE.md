# CLAUDE.md

このファイルは、Claude Code がこのリポジトリで作業する際のガイダンスを提供します。

## Rules

詳細なガイダンスは `.claude/rules/` ディレクトリを参照してください：

| Rule | Description |
|------|-------------|
| [product](.claude/rules/product.md) | プロダクト概要、目的、ターゲットユーザー |
| [structure](.claude/rules/structure.md) | ディレクトリ構成、命名規則 |
| [tech](.claude/rules/tech.md) | 技術スタック、ビルド・テストコマンド |
| [git](.claude/rules/git.md) | コミット・ブランチ・PR規約 |
| [behavior](.claude/rules/behavior.md) | 行動規約（調査優先、過剰設計禁止） |

## プロダクト概要

**⌘英かな (cmd-eikana)** — macOS用キーリマップユーティリティ（Apple Silicon Fork）

- 左右のコマンドキー単体押しで英数/かな切り替え
- キーリマップ設定で任意のキー変換が可能
- macOS 12.0+、Apple Silicon (arm64) 専用

## クイックリファレンス

### ビルド & テスト

```bash
# Releaseビルド
xcodebuild -project "⌘英かな.xcodeproj" -scheme "⌘英かな" \
  -configuration Release -arch arm64 clean build

# テスト実行
xcodebuild test -project "⌘英かな.xcodeproj" -scheme "⌘英かな" \
  -destination 'platform=macOS'
```

### プロジェクト構成

```
cmd-eikana/              # メインアプリ (Swift)
cmd-eikana-helper/       # ヘルパーアプリ (Objective-C, 自動起動用)
cmd-eikanaTests/         # ユニットテスト (XCTest)
docs/                    # GitHub Pages用ドキュメント
⌘英かな.xcodeproj/       # Xcodeプロジェクト
```

### 重要なルール

- **SwiftLint**: `force_cast`, `trailing_comma`, `opening_brace`, `closure_parameter_position` は無効化済み
- **Git**: `master`ブランチへの直接push禁止、コミットメッセージは日本語、Conventional Commits形式
- **Bundle ID**: `io.github.dominion525.cmd-eikana`
