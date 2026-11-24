# 筋トレ記録 iPhone v7（全データ同期版）

## v7でSupabase同期するもの
- 種目
- 種目の並び順
- 保存した筋トレメニュー
- トレーニング履歴
- 体重
- 体脂肪率

## 端末内に残すもの
- 週次CSVを出力済みかどうかの状態
- オフライン時のローカルコピー

## 初回ログイン時の移行
Supabase側に履歴や体組成データが無い場合、
現在端末のlocalStorageにある既存データをクラウドへ移行します。

## 必須
v7を使う前に、SupabaseのSQL Editorで
`SUPABASE_v7_SETUP.sql`
を実行してください。

## Project URL
https://fxbfgbjyomttenjkyrln.supabase.co

## セキュリティ
ブラウザ用Publishable keyのみ利用。
Secret/service_role keyは使用していません。
RLSでログイン本人のデータだけアクセス可能にします。

## 週次CSV
日曜〜土曜の7日分。
土曜日に起動すると案内し、未出力なら次回起動時にも案内します。
