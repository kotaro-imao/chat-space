# Chat-SpaceDB設計

## usersテーブル  
|Column|Type|Option|
|-------|----|------|
|email|strings|null: fales|
|password|strings|null: fales|
|name|strings|null: fales|
### Association  
- has_many :messages  
- has many :groups_users
- has many :groups, through: :groups_users

## groups_usersテーブル  
|Column|Type|Option|  
|------|-----|------|  
|user_id|integer|null: fales, foreign_key: true|  
|group_id|integer|null: fales, foreign_key: true|  
### Association  
- belongs_to :user  
- belongs_to :group  

## messagesテーブル  
|Column|Type|Option|  
|------|-----|------|  
|body|text|null: fales|  
|image|strings||  
|group_id|integer|null: fales, foreign_key: true|  
|user_id|integer|null: fales, foreign_key: true|  
### Association  
- belongs_to :user  
- belongs_to :group  

## groupsテーブル  
|Column|Type|Option|  
|-------|----|------|  
|group|strings|null: fales|  
|user_id|integer|null: fales|  
### Association   
- has_many :groups_users  
- has_many :users, through: :groups_users  
- belongs_to :massage  