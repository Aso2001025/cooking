```uml
@startuml
skinparam class {
    '図の背景
    BackgroundColor Snow
    '図の枠
    BorderColor Black
    'リレーションの色
    ArrowColor Black
}
!define MASTER_MARK_COLOR Orange 
!define TRANSACTION_MARK_COLOR DeepSkyBlue

package "スワプレ" as swap_recipes {
    /'
      マスターテーブルを M、トランザクションを T などで表記
      １文字なら "主" とか "従" まど日本語でも記載可能
     '/
    entity "食材マスタ" as foods <foods> <<M,MASTER_MARK_COLOR>> {
        + food_id [PK]
        --
        food_name
        # category_code [FK]
        food_image
        heating_flag
    }
    
    entity "カテゴリマスタ" as category <category> <<M,MASTER_MARK_COLOR>> {
        + category_cody [PK]
        --
        category_name
    }
    
    entity "メニューマスタ" as menu  <menu> <<M,MASTER_MARK_COLOR>> {
        + menu_id[PK]
        --
        menu_name
        menu_image
    }
    
    entity "メニュー詳細マスタ" as menu_datail <menu_datail> <<M,MASTER_MARK_COLOR>> {
        + menu_datil_id [PK]
        --
        # menu_id [FK]
        number 
        menu_data
    }
    
     entity "調理法マスタ" as procedure <procedure> <<M,MASTER_MARK_COLOR>> {
        + procedure_id [PK]
        --
        procedure_data
     }
    
    entity "レシピテーブル" as recipi <recipi> <<T,TRANSACTION_MARK_COLOR>> {
        + resipe_id [PK]
        --
        resipe_name
        # menu_id [FK]
        resipe_image
    }
    
    entity "レシピ食材テーブル" as recipi_food <recipi_food> <<T,TRANSACTION_MARK_COLOR>> {
        + recipi_id [PK]
        + food_id [PK]
    }
    
    entity "レシピ調理法テーブル" as recipi_procedure <recipi_procedure> <<T,TRANSACTION_MARK_COLOR>> {
        + recipi_id [PK]
        + procedure_id [PK]
    }
    
    entity "レシピ詳細テーブル" as recipi_datail <recipi_datail> <<T,TRANSACTION_MARK_COLOR>> {
        + recipi_datail_id [PK]
        --
        # recipi_id [FK]
        # food_id [FK]
        # procedure_id [FK]
        datail_data
    }
    
    entity "投稿テーブル" as post <post> <<T,TRANSACTION_MARK_COLOR>> {
        + post_id [PK]
        --
        # resipe_id [FK]
        nickname
        comment
        count
        date
    }
    
  }
  
foods               }o--||     category
menu                ||-r-o{     menu_datail
menu                |o-d-o{     recipi
foods               ||-l-o{     recipi_food
recipi_food         }o-r-||     recipi
recipi              ||-l-|{     recipi_procedure
recipi_procedure    }o-l-|| procedure
recipi              ||-r-|{     recipi_datail
recipi              ||---|{     foods
recipi              ||---|{     procedure
post                ||-l-|{     recipi
@enduml
```
