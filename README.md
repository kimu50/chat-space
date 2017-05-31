#DB設計

##Users table

|Column  |Type   |Options                        |
|:-------|:----- |:------------------------------|
|name    |string |null:false,add_index,index:true|
|email   |string |null:false,unique,true         |
|password|integer|null:false,unique,true         |

###Association

-has_many :messages

-has_many :group_users

-has_many :groups, through: :group_users


##Messages table

|Column  |Type   |Options                        |
|:-------|:----- |:------------------------------|
|body    |text   |null:false                     |
|image   |string |                               |
|user_id |integer|foreign_key:true               |
|group_id|integer|foreign_key:true               |

###Assotiation

-belongs_to :user

-belongs_to :group


##Group table

|Column    |Type   |Options                        |
|:---------|:----- |:------------------------------|
|name      |string |null:false,unique:true         |
|user_id   |integer|foreign_key:true               |
|message_id|integer|foreign_key:true               |

###Assotiation

-has_many :group_users

-has_many :users,through: :group_users

-has_many :messages


##Group_users table


|Column    |Type   |Options                        |
|:---------|:----- |:------------------------------|
|user_id   |integer|foreign_key:true               |
|message_id|integer|foreign_key:true               |

###Assotiation

-belongs_to :user

-belongs_to :message








