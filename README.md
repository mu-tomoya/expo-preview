# Expo PR Preview CI

このリポジトリは、Expo プロジェクトで Pull Request ごとに差分プレビューを作成するための CI 設定です。

CI は [expo-preview.yml](expo-preview.yml) を使って以下を自動実行します。

- PR をトリガーに EAS Update を作成
- 生成された Update Group ID を取得
- PR に Expo Go 用 QR コードと Update URL をコメント

## 事前準備

1. GitHub のリポジトリ Secrets に EXPO_TOKEN を登録
2. プロジェクトの app.json に expo.extra.eas.projectId が設定済みであることを確認
3. ワークフローを GitHub Actions で実行できる場所に配置

## ワークフロー概要

- Trigger: pull_request
- Runtime: ubuntu-latest
- Node.js: 24
- CLI: eas-cli (npm でインストール)

## 実行結果

PR に次の情報がコメントされます。

- Expo Go で読み取れる QR コード
- EAS Update の URL

これにより、レビュー中の PR 差分を実機ですばやく確認できます。
