# DB定義書
## ER図
[ER図はこちら](https://github.com/Aso2001025/cooking/blob/main/ER%E5%9B%B3.md)

# DBテーブルカラム一覧

# データベース設計図

## 食材テーブル(foods)
|和名|属性名(カラム名)|型|PK|NN|FK|
|---|-----|--|--|--|--|
|食材ID|food_id|bigint(20)|o|||
|食材名|food_name|varchar(50)||||
|カテゴリコード|category_code|int|||o|
|食材画像|food_image|varchar(200)||||
|加熱フラグ|heating_flag|int(1)||o||

## カテゴリテーブル(category)
|和名|属性名(カラム名)|型|PK|NN|FK|
|---|-----|--|--|--|--|
|カテゴリコード|category_cody|int(2)|○|○||
|カテゴリ名|category_name|varchar(50)|○|||

## メニューテーブル(menu)
|和名|属性名(カラム名)|型|PK|NN|FK|
|---|-----|--|--|--|--|
|メニューID|menu_id|bigint(100)|○|○||
|メニュー名|menu_name|varchar(50)||||
|メニュー画像|menu_image|varchar(200)||||

## メニュー詳細(menu_datail)
|和名|属性名(カラム名)|型|PK|NN|FK|
|---|-----|--|--|--|--|
|メニュー詳細ID|menu_datil_id|bigint(100)|o|o||
|メニューID|menu_id|bigint(100)|||o|
|調理手順|number|bigint(100)||||
|調理内容|menu_data|varchar(500)||o||

## 調理法テーブル(procedure)
|和名|属性名(カラム名)|型|PK|NN|FK|
|---|-----|--|--|--|--|
|調理法ID|procedure_id|bigint(100)|o|||
|調理内容|procedure_data|varchar(500)||||

##  レシピテーブル(recipi)
|和名|属性名(カラム名)|型|PK|NN|FK|
|---|-----|--|--|--|--|
|レシピID|resipe_id|bigint(100)|○|||
|レシピ名|resipe_name|varchar(500)||||
|メニューID|menu_id|bigint(100)|||o|
|レシピ画像|resipe_image|varchar(500)||||

## レシピ食材(recipi_food)
|和名|属性名(カラム名)|型|PK|NN|FK|
|---|-----|--|--|--|--|
|レシピID|recipi_id|bigint(100)|o||o|
|食材ID|food_id|bigint(100)|o||o|

## レシピ調理法(recipi_procedure)
|和名|属性名(カラム名)|型|PK|NN|FK|
|---|-----|--|--|--|--|
|レシピID|recipi_id|bigint(100)|o||o|
|調理法ID|procedure_id|bigint(100)|o||o|

## レシピ詳細(recipi_datail)
|和名|属性名(カラム名)|型|PK|NN|FK|
|---|-----|--|--|--|--|
|レシピ詳細ID|recipi_datail_id|bigint(100)|o|||
|レシピID|recipi_id|bigint(100)|||o|
|食材ID|food_id|bigint(100)|||o|
|調理法ID|procedure_id|bigint(100)|||o|
|詳細データ|datail_data|varchar(500)||||

## 投稿テーブル(post)
|和名|属性名(カラム名)|型|PK|NN|FK|
|---|-----|--|--|--|--|
|投稿ID|post_id|bigint(100)|o|||
|レシピID|resipe_id|bigint(100)|||o|
|ニックネーム|nickname|varchar(100)||||
|コメント|comment|varchar(500)||||
|いいね数（BAD数）|count|int(21)||||
|投稿日|date|date||||
