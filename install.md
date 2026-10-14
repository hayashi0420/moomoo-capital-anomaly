# moomoo 資金フロー異常検知 Skill インストールガイド

本ドキュメントは、moomoo 資金フロー異常検知 Skill を Claude Code 環境へ導入する手順を説明します。

## 前提条件

- Claude Code CLI がインストール済みであること
- moomoo OpenAPI の認証設定が完了していること
- Python 3.x が利用可能であること
- UNIX 系コマンド(curl, openssl, date)が利用可能であること(Windows の場合は Git Bash 環境を推奨)

## インストール手順

### Step 1: リポジトリのクローン

以下のコマンドをターミナルで実行し、Skill ファイル一式をローカルに取得します。

```bash
git clone https://github.com/alicialin0420/moomoo-capital-anomaly.git
```

### Step 2: Skill ディレクトリへの配置

クローンした `SKILL.md` および `scripts/` ディレクトリを Claude Code の Skill 格納ディレクトリに配置します。

#### macOS / Linux の場合

```bash
mkdir -p ~/.claude/skills/moomoo-capital-anomaly
cp moomoo-capital-anomaly/SKILL.md ~/.claude/skills/moomoo-capital-anomaly/
cp -r moomoo-capital-anomaly/scripts ~/.claude/skills/moomoo-capital-anomaly/
```

#### Windows の場合

```powershell
New-Item -ItemType Directory -Force -Path $env:USERPROFILE\.claude\skills\moomoo-capital-anomaly
Copy-Item moomoo-capital-anomaly\SKILL.md $env:USERPROFILE\.claude\skills\moomoo-capital-anomaly\
Copy-Item -Recurse moomoo-capital-anomaly\scripts $env:USERPROFILE\.claude\skills\moomoo-capital-anomaly\
```

### Step 3: 設定の反映

Claude Code を再起動する、または新しいセッションを開始することで、Skill が認識されます。

### Step 4: 動作確認

Claude Code 上で以下のように呼び出し、Skill が反応することを確認します。

```
US.NVDA の資金異動を検知して
```

または

```
HK.00700 の資金フロー異常検知をお願い
```

## アンインストール手順

Skill ディレクトリを丸ごと削除してください。

```bash
rm -rf ~/.claude/skills/moomoo-capital-anomaly
```

## トラブルシューティング

### Skill が認識されない場合

- `~/.claude/skills/moomoo-capital-anomaly/` ディレクトリが存在するか確認してください
- ディレクトリ内に `SKILL.md` が存在するか確認してください
- `scripts/handle_capital_anomaly.py` が配置済みか確認してください
- Claude Code を完全に再起動してください

### Python スクリプトが動かない場合

- Python 3.x がインストールされているか確認してください
- 必要な依存パッケージ(moomoo OpenAPI SDK 等)がインストールされているか確認してください

### API 認証エラーが出る場合

- moomoo OpenAPI の認証設定が完了しているか確認してください
- OpenD が起動済みであるか確認してください

## サポート

不具合や改善要望は本リポジトリの Issue よりご報告ください。
