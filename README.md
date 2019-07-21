## usersテーブル

|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|index: true|

### Association
- has_many :groups, through: :members
- has_many :chats

## groupsテーブル

|column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- belongs_to :chat

## chatsテーブル

|column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|


### Association
- belongs_to :group
- belongs_to :user

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user