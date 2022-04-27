# データベース設計図

## foods
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|food_id|bigint(20)|o|||
|food_name|varchar(50)||||
|category_cody|int|||o|
|food_image|varchar(200)||||
|heating_flag|int(1)||o||


## category
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|category_cody|int(2)|○|○||
|category_name|varchar(50)|○|||


## menu
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|menu_id|bigint(100)|○|○||
|menu_name|varchar(50)||||
|menu_image|varchar(200)||||


## menu_datail
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|menu_datil_id|bigint(100)|o|o||
|menu_id|bigint(100)|||o|
|number|bigint(100)||||
|menu_data|varchar(500)||o||


## procedure
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|procedure_id|bigint(100)|o|||
|procedure_data|varchar(500)||||



##  recipi
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|resipe_id|bigint(100)|○|||
|resipe_name|varchar(500)||||
|menu_id|bigint(100)|||o|
|resipe_image|varchar(500)||||

## recipi_food
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|recipi_id|bigint(100)|o||o|
|food_id|bigint(100)|o||o|

## recipi_procedure
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|recipi_number_id|bigint(100)|o|||
|recipi_id|bigint(100)|||o|
|procedure_id|bigint(100)|||o|

## recipi_datail
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|recipi_datail_id|bigint(100)|o|||
|recipi_id|bigint(100)|o||o|
|food_id|bigint(100)|o||o|
|food_id|bigint(100)|||o|
|datail_data|varchar(500)||||

## post
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|post_id|bigint(100)|o|||
|resipe_id|bigint(100)|||o|
|nickname|varchar(100)||||
|comment|varchar(500)||||
|count|int(21)||||
|date|date||||
