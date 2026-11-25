# 筋トレ記録 iPhone v6（Supabase同期版）

## Supabase
Project URL:
https://fxbfgbjyomttenjkyrln.supabase.co

ブラウザ用 Publishable key を使用しています。
Secret key / service_role key は使用していません。

## クラウド同期するもの
- 種目名
- 種目の並び順
- 保存した筋トレメニュー

## 端末内に保存するもの（v6ではまだ同期しません）
- トレーニング履歴
- 体重
- 体脂肪率
- 週次CSVの出力済み状態

## 初回ログイン
Supabase側の exercises が空の場合、現在端末に保存されている種目・並び順・保存メニューをクラウドへ移行します。

## 必要なSupabaseテーブル
- exercises(id, user_id, name, sort_order, created_at)
- workout_menus(id, user_id, name, exercise_ids, created_at)

RLSを有効にし、ログイン本人だけがCRUDできるポリシーが必要です。

## 週次CSV
日曜日〜土曜日の7日分。
土曜日に起動すると案内し、未出力なら次回起動時にも案内します。
