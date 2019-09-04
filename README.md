# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|nique: true, null: false, add_index|
|name|string|null: false|
|email|string|nique: true, null: false|
|password|string|null: false|
|created_at|timestamp|null: false|
|updated_at|timestamp|null: false|

### Association
- has_many :users_groups
- has_many :groups through: :users_groups
- has_many :messages

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|nique: true, null: false,, add_index|
|name|string|null:false|
|created_at|timestamp|null: false|
|updated_at|timestamp|null: false|

### Association
- has_many :users_groups
- has_many :users through: :users_groups
- has_many :messages

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|nique: true, null: false, add_index|
|body|text|null:false|
|image|string||
|user_id|int|null:false, foreign_key: true|
|group_id|int|null:false, foreign_key: true|
|created_at|timestamp|null: false|
|updated_at|timestamp|null: false|

### Association
- belongs_to :user
- belongs_to :group

## users_groupsテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|nique: true, null: false|
|user_id|int|null:false, foreign_key: true, add_index|
|group_id|int|null:false, foreign_key: true, add_index|
|created_at|timestamp|null: false|
|updated_at|timestamp|null: false|

### Association
- belongs_to :user
- belongs_to :group
