# プロジェクト構成

## ディレクトリレイアウト

```
cmd-eikana/                  # メインアプリ (Swift)
├── AppDelegate.swift        # アプリライフサイクル、ステータスバーメニュー
├── KeyEvent.swift           # キーイベント監視・処理（CGEvent tap）
├── KeyMapping.swift         # キーマッピング定義・管理
├── KeyboardShortcut.swift   # ショートカット管理（修飾キー + キーコード）
├── ShortcutsController.swift # ショートカットUI制御（テーブルビュー）
├── ViewController.swift     # メイン設定画面
├── AppData.swift            # アプリデータ管理（UserDefaults）
├── checkUpdate.swift        # GitHub Releases APIによるアップデートチェック
├── toggleLaunchAtStartup.swift # ログイン時自動起動設定（SMAppService）
├── ExclusionAppsController.swift # 除外アプリ管理UI
├── KeyTextField.swift       # キー入力用カスタムテキストフィールド
├── MappingMenu.swift        # マッピングメニュー
├── MediaKeyEvent.swift      # メディアキーイベント処理
├── PreferenceWindowController.swift # 設定ウィンドウ管理
├── Assets.xcassets/         # アプリアイコン等
├── Base.lproj/              # Storyboard（Main.storyboard）
├── ja.lproj/                # 日本語ローカライズ
└── Info.plist               # アプリ設定

cmd-eikana-helper/           # ヘルパーアプリ (Objective-C)
├── AppDelegate.{h,m}        # ヘルパーアプリのエントリーポイント
├── main.m                   # main関数
└── Info.plist               # ヘルパー設定

cmd-eikanaTests/             # ユニットテスト (XCTest)
├── AppDataTests.swift       # AppDataのテスト
├── CheckUpdateTests.swift   # アップデートチェックのテスト
├── KeyboardShortcutTests.swift # ショートカット関連テスト
├── KeyboardShortcutFlagTests.swift # 修飾キーフラグテスト
├── KeyMappingTests.swift    # キーマッピングテスト
├── ShortcutsControllerTests.swift # ショートカットコントローラーテスト
├── LaunchAtStartupMigrationTests.swift # 自動起動マイグレーションテスト
├── KeyboardShortcutTestHelper.swift # テストヘルパー
└── CmdEikanaTests.swift     # 基本テスト

docs/                        # GitHub Pages用ドキュメント・画像
⌘英かな.xcodeproj/           # Xcodeプロジェクト
.github/workflows/build.yml  # CI設定
.swiftlint.yml               # SwiftLint設定
```

## ファイル命名規則

| 種類 | 規則 | 例 |
|------|------|-----|
| Swiftソースファイル | PascalCase | `KeyEvent.swift` |
| ユーティリティ関数 | camelCase | `checkUpdate.swift`, `toggleLaunchAtStartup.swift` |
| テストファイル | *Tests.swift | `KeyMappingTests.swift` |
| テストヘルパー | *TestHelper.swift | `KeyboardShortcutTestHelper.swift` |
