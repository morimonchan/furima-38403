# README

# テーブル設計

＊users テーブル

| Column             | Type   | Options                |
| ------------------ | ------ | -----------            |
| nickname           | string | null: false            |
| email              | string | null: false default: ""|
| encrypted_password | string | null: false default: ""|
| name_last          | string | null: false            |
| name_first         | string | null: false            |
| name_kana_ last    | string | null: false            |
| name_kana_first    | string | null: false            |
| birthday           | integer| null: false            |

- belongs_to :item
- belongs_to :price

＊items テーブル
| Column             | Type   | Options                |
| ------------------ | ------ | -----------            |
| image              | text   | null: false            |
| name               | string | null: false            |
| explain            | text   | null: false            |
| category           | string | null: false            |
| condition          | string | null: false            |
| cost_burden        | string | null: false            |
| place              | string | null: false            |
| day                | integer| null: false            |

- has_many :users
- belongs_to :price

＊prices テーブル
| Column             | Type   | Options                |
| ------------------ | ------ | -----------            |
| price              | integer| null: false            |

- belongs_to :user
- belongs_to :item
- belongs_to :sent

＊sents テーブル
| Column             | Type    | Options                 |
| ------------------ | ------- | -----------             |
| number             | integer | null: false             |
| exp_month          | integer | null: false default: "" |
| cvc                | integer | null: false default: "" |
| code               | integer | null: false             |
| prefectures        | string  | null: false             |
| city               | string  | null: false             |
| street_address     | string  | null: false             |
| building           | string  |                         |
| phone_number       | integer | null: false          |


- belongs_to :price