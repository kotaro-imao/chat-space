# Chat-SpaceDB設計

## userテーブル  
|Column｜Type|Option|  
|-------|----|------|  
|email|strings|null: fales|  
|password|strings|null: fales|  
|name|strings|null: fales|  
### Association  
- has_many :massages  

## groupoes_usersテーブル  
|Column｜Type|Option|  
|------|-----|------|  
|user_id|integer|null: fales, foreign_key: true|  
|groupes_id|integer|null: fales, foreign_key: true|  
### Association  
- has_many :comments  

## massageテーブル  
|Column｜Type|Option|  
|------|-----|------|  
|body|text|null: fales|  
|image|string|null: fales|  
|time|integer|null: fales|  
|groupe_id|integer|null: fales, foreign_key: true|  
|user_id|integer|null: fales, foreign_key: true|  
### Association  
- belongs_to :user  