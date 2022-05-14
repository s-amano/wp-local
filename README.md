# WordPressローカル開発環境構築

```sh
$ mkdir mylocal-wordpress
$ cd mylocal-wordpress
$ touch docker-compose.yml
$ mkdir db_data
$ mkdir wordpress
```

```sh
.mylocal-wordpress
├── db_data
├── wordpress
└── docker-compose.yml
```

### データを持ってくる

`wp-content`と`wp-config.php`を本番環境のものにする。

また、dbデータを持ってくる。

```
.mylocal-wordpress
├── db_data
│    └── exportしてきたsqlファイル名.sql
├── wordpress
│   ├── wp-content
│   └── wp-config.php
└── docker-compose.yml
```

### wp-config.phpを編集する

`DB_NAME`, `DB_USER`, `DB_PASSWORD`, `DB_HOST`をdocker-compose.ymlに記載したものに変更。

### 一旦

`
$ docker-compose up -d
`
  
で、http://localhost:8000/

### urlをlocalに入れ替える

```
$ cd wordpress/
$ git clone https://github.com/interconnectit/Search-Replace-DB.git
```

```sh
$ docker-compose down
$ docker-compose up -d
```

http://localhost:8000/Search-Replace-DB/
にいく。

- replace: 「https://blog.hpfull.jp」 with 「http://localhost:8000」
- database name: 「wordpress」
- username: 「wordpress」
- pass: 「wordpress」
- host: 「db」
- port: 「3306」
- host: 「db」

として「Search and Replace」をクリック。









