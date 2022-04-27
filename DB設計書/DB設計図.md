# データベース設計図

## Food 
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|food_id|bigint(20)|○|○|
|food_name|varchar(50)|○||
|category_cody|int|○|
|food_image|varchar(200)○|
|heating_flag|int(1)||


## category
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|category_cody|int(2)|○|○
|category_name|varchar(50)○


## recipe
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|recipe_id|bigint(100)|○|○
|recipe_name|varchar(50)○|
|recipe_deta|varchar(50)○|


## recipe_detail
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|recipe_id|bigint(100)|○|○
|recipe_name|varchar(50)○
|recipe_deta|varchar(50)○|


## procedure
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|recipi_id|bigint(100)|○|○
|Itinerary|varchar(50)○
|order|int(100)○


##  Itinerary
|項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|resipe_id|bigint(100)|○|○
|Itinerary|varchar(50)○



## order
項目名|型|PK|NN|FK|
|-----|--|--|--|--|
|resipe_id|bigint(100)|○|○
|order|int(100)○||
