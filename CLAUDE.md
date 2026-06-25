# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Git運用ルール

- コードを変更したら、その都度コミットしてGitHubにプッシュすること。

## デプロイ先

https://claudetsukattemiru-crypto.github.io/task-board/

`main`ブランチへのpushをトリガーに、`.github/workflows/deploy.yml`がビルドしてGitHub Pagesへ自動デプロイする。

## 技術スタック

- React 19 + Vite 8（`@vitejs/plugin-react`）
- Lint: oxlint（`npm run lint`）
- 状態の永続化はブラウザの`localStorage`を使用（バックエンド・DBなし）
- TypeScriptは未導入（`.jsx`の素のJavaScript）

## コンポーネントの命名規約

- コンポーネントファイルは`PascalCase.jsx`（例: `App.jsx`）とし、対応するスタイルは同名の`PascalCase.css`を同階層に置く。
- イベントハンドラ関数は`handle`から始める（例: `handleAddTask`）。状態更新のみを行う関数は対象の動詞で始める（例: `toggleTask`, `deleteTask`）。
- `localStorage`のキー名など定数は`UPPER_SNAKE_CASE`で定義する（例: `STORAGE_KEY`）。
