# OpenAI.fm

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
![NextJS](https://img.shields.io/badge/Built_with-NextJS-blue)
![OpenAI API](https://img.shields.io/badge/Powered_by-OpenAI_API-orange)

**English:** A TTS demo app (PoC) based on [OpenAI.fm](https://openai.fm). Try Voice / Vibe / Script and copy your preferred settings with one click. Access is protected by Basic auth.

**日本語:** [OpenAI.fm](https://openai.fm) をベースにした TTS デモアプリ（PoC）。Voice / Vibe / Script を試して、気に入った設定をワンクリックでコピーして共有できます。Basic 認証によるアクセス制限付き。

---

## Setup | セットアップ

### Prerequisites | 前提条件

- [Bun](https://bun.sh/) installed | [Bun](https://bun.sh/) がインストールされていること
- [OpenAI API key](https://platform.openai.com/api-keys) | [OpenAI API キー](https://platform.openai.com/api-keys) を取得済みであること

### 1. Clone the repository | リポジトリのクローン

```bash
git clone <your-repo-url>
cd openai-fm
```

### 2. Environment variables | 環境変数の設定

Create a `.env` file from `.env.example`.  
`.env.example` を参考に `.env` ファイルを作成します。

```bash
cp .env.example .env
```

Edit `.env`:

```bash
# Required | 必須: OpenAI API key
OPENAI_API_KEY=sk-...

# Optional | 任意: Basic auth (enabled when both are set)
BASIC_AUTH_USER=admin
BASIC_AUTH_PASSWORD=your-password-here
```

### 3. Install dependencies | 依存パッケージのインストール

```bash
bun install
```

### 4. Start the dev server | 開発サーバーの起動

```bash
bun run dev
```

The app runs at [`http://localhost:3000`](http://localhost:3000).  
[`http://localhost:3000`](http://localhost:3000) でアプリが起動します。

---

## Deploy to Vercel | Vercel へのデプロイ

1. Push the repository to GitHub | GitHub にリポジトリを push
2. Import the project on [Vercel](https://vercel.com/new) | [Vercel](https://vercel.com/new) でプロジェクトをインポート
3. Set Environment Variables | Environment Variables に以下を設定:
   - `OPENAI_API_KEY`
   - `BASIC_AUTH_USER`
   - `BASIC_AUTH_PASSWORD`
4. Deploy | デプロイ実行

> [!NOTE]
> **EN:** OpenAI API usage on the deployed app is billed to the owner of the API key. Enable Basic auth to prevent unintended access.  
> **JA:** デプロイ先で発生する OpenAI API の利用料金は、設定した API キーの所有者に請求されます。Basic 認証を必ず有効にして、意図しないアクセスを防いでください。

---

## Changes from the original | オリジナルからの変更点

- Share feature (Postgres) removed | シェア機能（Postgres 連携）を削除
- “Copy Settings” button added (Voice / Language / Vibe to clipboard) | 「Copy Settings」ボタンを追加（Voice / Language / Vibe をクリップボードにコピー）
- Basic auth middleware added | Basic 認証ミドルウェアを追加
- Package manager unified to bun | パッケージマネージャーを bun に統一

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

Based on [openai/openai-fm](https://github.com/openai/openai-fm).
