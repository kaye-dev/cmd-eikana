# Git規約

## コミットメッセージ

コミットメッセージは**日本語**で生成してください（指示がない限り）。

### コミット種別（Conventional Commits）

| 種別 | 用途 |
|------|------|
| `feat` | 新機能追加 |
| `fix` | バグ修正 |
| `chore` | ビルド、設定、バージョン更新等 |
| `docs` | ドキュメント変更 |
| `refactor` | リファクタリング（機能変更なし） |
| `test` | テスト追加・修正 |

### メッセージフォーマット

```
種別: 変更の概要
```

大規模な変更の場合:

```
種別: 変更の概要

- 変更点1
- 変更点2
```

### 例

```
fix: Key Remapの削除・無効化ができない問題を修正
```

```
feat: Key RemapのEnable/Disable機能を実装
```

```
chore: バージョンを2.4.2に更新
```

### 禁止事項

- `🤖 Generated with [Claude Code]` などの署名行
- `Co-Authored-By: Claude <noreply@anthropic.com>` などの共著者情報
- その他Claude関連のメタ情報

## ブランチ

### ルール

- `master`ブランチへの直接push禁止
- 全ての作業はfeatureブランチで行う

### ブランチ命名規則

```
種別/説明
```

例: `fix/key-remap-delete`, `feat/media-key-support`

### メインブランチ

- **`master`**: PRのベースブランチ
- `main`ブランチも存在するが、PRは`master`に対して作成する

## Pull Request

### 基本構成

```markdown
## 変更の概要
この変更で何を実現したかを簡潔に説明

## 変更内容
- 変更点1
- 変更点2

## 動作確認
実施した動作確認の内容
```
