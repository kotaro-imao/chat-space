# Chat-SpaceDB設計

## usersテーブル  
|Column|Type|Option|
|-------|----|------|
|email|string|null: fales|
|password|string|null: fales|
|name|string|null: fales|
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
|body|text||  
|image|string||  
|group_id|integer|null: fales, foreign_key: true|  
### Association  
- belongs_to :group  

## groupsテーブル  
|Column|Type|Option|  
|-------|----|------|  
|group|string|null: fales|  
|user_id|integer|null: fales|  
### Association   
- has_many :groups_users  
- has_many :users, through: :groups_users  
- has_many :message  