# Chat-SpaceDB設計

## usersテーブル  
|Column|Type|Option|
|-------|----|------|
|email|strings|null: fales|
|password|strings|null: fales|
|name|strings|null: fales|
### Association  
- has_many :messages  

## groupoes_usersテーブル  
|Column｜Type|Option|  
|------|-----|------|  
|user_id|integer|null: fales, foreign_key: true|  
|groupe_id|integer|null: fales, foreign_key: true|  
### Association  
- belongs_to :user  
- belongs_to :groupe  

## massagesテーブル  
|Column｜Type|Option|  
|------|-----|------|  
|body|text|null: fales|  
|image|strings||  
|groupe_id|integer|null: fales, foreign_key: true|  
|user_id|integer|null: fales, foreign_key: true|  
### Association  
- belongs_to :user  
- belongs_to :groupe  

## groupesテーブル  
|Column｜Type|Option|  
|-------|----|------|  
|groupe|strings|null: fales|  
|user_id|integer|null: fales|  
### Association   
- has_many :groupes_users  
- has_many :users  , through: groupes_users  