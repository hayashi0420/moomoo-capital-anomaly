# moomoo 資金フロー異常検知 Skill

moomoo OpenAPI の `get_financial_unusual` を呼び出し、指定銘柄の資金分布・買売経紀商・資金流向・空売り数量・空売り比例などの資金フロー系データを取得して、異常変動を検知する Claude Code 用 Skill です。

## 機能概要

- 指定銘柄の資金分布データを取得
- 買い・売り経紀商別の取引状況を可視化
- 資金流向(純流入・純流出)を判定
- 空売り数量・空売り比例の異常変動を検知
- 検知結果を構造化されたレポートとして出力

## 想定ユースケース

- 「主力資金が入っているか・出ているか」を確認したい
- 「誰が買って・誰が売っているか」を把握したい
- 空売りの異常増加・減少を検知したい
- 銘柄の資金フローに基づく異動検知を行いたい
- 広域異動リクエスト(「NVDA 異動」「テンセント異常ある?」等)で資金面を一括分析したい

## 必要環境

- Claude Code CLI または Claude Agent SDK
- moomoo OpenAPI 認証設定済み環境
- curl / openssl / date コマンド(Linux・macOS 標準搭載、Windows は Git Bash 推奨)

## 同梱ファイル

- `SKILL.md` — Skill 本体
- `scripts/handle_capital_anomaly.py` — 異常検知スクリプト

## インストール

インストール手順は [install.md](./install.md) を参照してください。

## ライセンス

MIT License

## 作者

Futu
