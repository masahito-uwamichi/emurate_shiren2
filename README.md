# emurate_shiren2
開発技法を試しながら風来のシレン２的なシステムを作っていく予定です

## 開発環境のセットアップ

このプロジェクトはRustで開発されており、DockerまたはPodmanを使用してコンテナ化された開発環境を提供しています。

### 前提条件

以下のいずれかをインストールしてください：
- Docker Desktop + VS Code + Dev Containers拡張機能
- Podman + VS Code + Dev Containers拡張機能

### セットアップ方法

#### 方法1: VS Code DevContainer（推奨）

1. VS Codeでプロジェクトを開く
2. コマンドパレット（Ctrl+Shift+P）を開く
3. "Dev Containers: Reopen in Container" を実行
4. 初回起動時はコンテナのビルドに数分かかります

#### 方法2: Docker Compose

```bash
# コンテナを起動
docker-compose up -d

# コンテナに接続
docker-compose exec rust-dev bash

# 開発完了後、コンテナを停止
docker-compose down
```

#### 方法3: Podman Compose

```bash
# コンテナを起動
podman-compose up -d

# コンテナに接続
podman-compose exec rust-dev bash

# 開発完了後、コンテナを停止
podman-compose down
```

### 開発環境の特徴

- **Rust 1.75**: 最新の安定版Rust
- **便利なツール**: clippy、rustfmt、cargo-edit、cargo-watch等が事前インストール済み
- **VS Code統合**: Rust Analyzer、LLDB デバッガー等の拡張機能が自動インストール
- **永続化されたキャッシュ**: Cargoのキャッシュとtargetディレクトリが永続化され、ビルドが高速化

### よく使うコマンド

```bash
# 新しいRustプロジェクトを作成
cargo new my_project

# 依存関係をビルド
cargo build

# テストを実行
cargo test

# コードをフォーマット
cargo fmt

# リンターを実行
cargo clippy

# ファイル変更を監視して自動ビルド
cargo watch -x build
```
