# プロダクト概要

## Product Name

⌘英かな (cmd-eikana) — Apple Silicon Fork

## Purpose

macOS用のキーリマップユーティリティ。左右のコマンドキーを単体で押した時に英数/かなを切り替える。設定によりキーリマップアプリとしても利用可能。

## Origin

[iMasanari/cmd-eikana](https://github.com/iMasanari/cmd-eikana) のフォーク版。

### オリジナル版との違い

- Apple Silicon (arm64) 専用ビルド
- 最小動作要件: macOS 12.0 (Monterey) 以降
- Bundle ID: `io.github.dominion525.cmd-eikana`
- 署名・公証対応

## Target Users

- macOSでJIS配列的な英数/かな切り替えを使いたいユーザー
- US配列キーボードでコマンドキーを活用したいユーザー
- キーリマップをカスタマイズしたいパワーユーザー

## Key Features

- コマンドキー単体押しで英数/かな切り替え
- キーリマップ設定（任意のキー → 任意のキー）
- キーリマップのEnable/Disable切り替え
- 除外アプリ設定
- ログイン時の自動起動
- アップデートチェック
- ステータスバーメニュー

## 動作要件

- macOS 12.0 (Monterey) 以降
- Apple Silicon (arm64)
- アクセシビリティ権限（キーイベント監視に必須）

## 設定ファイル

- `~/Library/Preferences/io.github.dominion525.cmd-eikana.plist`
