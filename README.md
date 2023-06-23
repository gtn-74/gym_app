## usersテーブル
| Column              | Type       | Options                        |
| ------------------  | ---------- | ------------------------------ |
| nickname            | string     | not null                       |
| email               | string     | not null  unique: true         |
| encrypted_password  | string     | not null                       |
| family_name         | string     | not null                       |
| first_name          | string     | not null                       |
| family_name_kana    | string     | not null                       |
| first_name_kana     | string     | not null                       |
| birth_day           | date       | not null                       |
| club_team           | string     | not null                       |

### Association
- has_many :indexs
- has_many :performances

## indexテーブル
| Column              | Type       | Options                        |
| ------------------  | ---------- | ------------------------------ |
| performance_meeting | string     | null false                     |
| user_id             | references | null false  foreign_key: true  |
| performance_id      | references | null false  foreign_key: true  |

### Association
- belongs_to :user
- has_many :performances

## performanceテーブル
| Column              | Type       | Options                        |
| ------------------  | ---------- | ------------------------------ |
| d_score             | integer    | null false                     |
| e_score             | integer    | null false                     |
| event_score         | integer    | null false                     |
| event               | string     | null false                     |
| user_id             | references | null false  foreign_key: true  |
| index_id            | references | null false  foreign_key: true  |

### Association
- belongs_to :user
- belongs_to :performance