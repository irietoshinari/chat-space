## userテーブル 
|Column|Type|Options|
|------|----|-------|   
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
### Association
- has_many :messages
- has_many :group_user
- has_many :groups,through: group_user

## groups_テーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many : messages
- has_many : group_user
- has_many :users, through: group_user

### messages_テーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group
## group_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user
