# 技術スタック

## 言語

- **Swift**: メインアプリ（`cmd-eikana/`）
- **Objective-C**: ヘルパーアプリ（`cmd-eikana-helper/`、自動起動用）

## フレームワーク

- **AppKit / Cocoa**: UI、ステータスバーメニュー、設定画面
- **CoreGraphics**: キーイベント監視（`CGEvent`, `CGEventTap`）
- **ServiceManagement**: ログイン時自動起動（`SMAppService`）

## ビルドシステム

- **Xcode**: `⌘英かな.xcodeproj`
- **ターゲットアーキテクチャ**: arm64 (Apple Silicon)
- **Deployment Target**: macOS 12.0

## リンター

- **SwiftLint**: `.swiftlint.yml`
  - 無効化ルール: `force_cast`, `trailing_comma`, `opening_brace`, `closure_parameter_position`
  - 除外: `Pods/`, `DerivedData/`

## テスト

- **XCTest**: `cmd-eikanaTests/`
- CI実行: `xcodebuild test -project "⌘英かな.xcodeproj" -scheme "⌘英かな" -destination 'platform=macOS'`

## CI/CD

- **GitHub Actions**: `.github/workflows/build.yml`
  - ランナー: `macos-15`
  - テスト実行 + Releaseビルド（署名なし）

## ビルドコマンド

```bash
# Releaseビルド
xcodebuild -project "⌘英かな.xcodeproj" -scheme "⌘英かな" \
  -configuration Release -arch arm64 clean build

# テスト実行
xcodebuild test -project "⌘英かな.xcodeproj" -scheme "⌘英かな" \
  -destination 'platform=macOS'

# CI環境（署名なし）
xcodebuild test -quiet -project "⌘英かな.xcodeproj" -scheme "⌘英かな" \
  -destination 'platform=macOS' \
  CODE_SIGN_IDENTITY="-" CODE_SIGNING_REQUIRED=NO CODE_SIGNING_ALLOWED=NO
```
