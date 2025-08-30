# CLAUDE.md

このファイルは、このリポジトリ内のコードを操作する際に Claude Code にガイダンスを提供します。

## 技術要件

### フロントエンド(frontend)
- **React Native**: Expo SDK
- **ナビゲーション**: expo-router
- **状態管理**: Zustand (Class構文を使ったストア定義)
- **UIライブラリ**: react-native-paper, react-native-safe-area-context
- **Bottom Tab**: react-native-bottom-tabs
- **データ永続化**: @react-native-async-storage/async-storage
- **通知**: expo-notifications
- **多言語対応**: react-i18next
- **フォーム**: react-hook-form
- **アイコン**: react-icons
- **HTTP通信**: axios（一般用途）, fetch（エラーサーバ通信用）
- **Drag And Drop**: @mgcrea/react-native-dnd
- **言語**: JavaScript（TypeScriptは使わない）

### バックエンド(backend)
- **Webフレームワーク**: FastAPI(Python 3)
- **データベース**: SQLite

### アーキテクチャ
- **設計パターン**: クリーンアーキテクチャ
  - Domain Layer（ビジネスロジック）
  - Infrastructure Layer（データアクセス）
  - Presentation Layer（UI）
- **データ正規化**: 第1〜第3正規化対応
- **データバージョニング**: バージョン情報付きマイグレーション対応

### テスト
- **Unitテスト**: jest-expo
- **React Nativeテスト**: @testing-library/react-native
