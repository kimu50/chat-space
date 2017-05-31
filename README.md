# DB設計

## Users table

|Column  |Type   |Options                          |
|:-------|:----- |:--------------------------------|
|name    |string |null:false,index:true,unique:true|

### Association

- has_many :messages

- has_many :group_users

- has_many :groups, through: :group_users


## Messages table

|Column  |Type   |Options                        |
|:-------|:----- |:------------------------------|
|body    |text   |null:false                     |
|image   |string |null:false                     |
|user_id |integer|foreign_key:true,null:false    |
|group_id|integer|foreign_key:true,null:false    |

### Assotiation

- belongs_to :user

- belongs_to :group


## Groups table

|Column     |Type   |Options                        |
|:----------|:----- |:------------------------------|
|name       |string |null:false,unique:true         |


### Assotiation

- has_many :group_users

- has_many :users,through: :group_users

- has_many :messages


## Group_users table


|Column    |Type   |Options                        |
|:---------|:----- |:------------------------------|
|user_id   |integer|foreign_key:true,null:false    |
|message_id|integer|foreign_key:true,null:false    |

### Assotiation

- belongs_to :user

- belongs_to :group








