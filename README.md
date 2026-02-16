# OpenAI.fm

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
![NextJS](https://img.shields.io/badge/Built_with-NextJS-blue)
![OpenAI API](https://img.shields.io/badge/Powered_by-OpenAI_API-orange)

[OpenAI.fm](https://openai.fm) をベースにした TTS デモアプリ（PoC）。
Voice / Vibe / Script を試して、気に入った設定をワンクリックでコピーして共有できます。

Basic 認証によるアクセス制限付き。

![screenshot](./public/screenshot.jpg)

## セットアップ

### 前提条件

- [Bun](https://bun.sh/) がインストールされていること
- [OpenAI API キー](https://platform.openai.com/api-keys) を取得済みであること

### 1. リポジトリのクローン

```bash
git clone <your-repo-url>
cd openai-fm
```

### 2. 環境変数の設定

`.env.example` を参考に `.env` ファイルを作成します。

```bash
cp .env.example .env
```

`.env` を編集:

```bash
# 必須: OpenAI API キー
OPENAI_API_KEY=sk-...

# 任意: Basic 認証（両方設定すると有効化）
BASIC_AUTH_USER=admin
BASIC_AUTH_PASSWORD=your-password-here
```

### 3. 依存パッケージのインストール

```bash
bun install
```

### 4. 開発サーバーの起動

```bash
bun run dev
```

[`http://localhost:3000`](http://localhost:3000) でアプリが起動します。

## Vercel へのデプロイ

1. GitHub にリポジトリを push
2. [Vercel](https://vercel.com/new) でプロジェクトをインポート
3. Environment Variables に以下を設定:
   - `OPENAI_API_KEY`
   - `BASIC_AUTH_USER`
   - `BASIC_AUTH_PASSWORD`
4. デプロイ実行

> [!NOTE]
> デプロイ先で発生する OpenAI API の利用料金は、設定した API キーの所有者に請求されます。
> Basic 認証を必ず有効にして、意図しないアクセスを防いでください。

## オリジナルからの変更点

- シェア機能（Postgres 連携）を削除
- 「Copy Settings」ボタンを追加（Voice / Vibe / Script をクリップボードにコピー）
- Basic 認証ミドルウェアを追加
- パッケージマネージャーを bun に統一

## License

This project is licensed under the MIT License. See the LICENSE file for details.

Based on [openai/openai-fm](https://github.com/openai/openai-fm).
