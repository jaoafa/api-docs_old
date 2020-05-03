# Resources/Club

- [TopPage](/api-docs/)

clubjaoafa 関連 API  
[/clubjaoafa](/api-docs/clubjaoafa)も参考。

## Get User (From UserToken)

- **GET** `/club/@me`

ユーザートークンから clubjaoafa アカウント情報を取得する。

### Request Parameters

このエンドポイントのパラメータはすべて Optional ですが、いずれかのパラメータがなければなりません。

| Field       | Description | Example                          | Remarks         |
| :---------- | :---------- | :------------------------------- | :-------------- |
| `usertoken` | UserToken   | XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX | 32 桁、英数字。 |

### Response

[基本レスポンス](/api-docs/topics/basic-response)に加え、以下が返却されます。

| Field  | Description                                                        | Example | Remarks |
| :----- | :----------------------------------------------------------------- | :------ | :------ |
| `data` | [clubjaoafa アカウントオブジェクト](/api-docs/object/club-account) |         |         |

## Get Token

- **GET** `/club/token`

ユーザーの入力したログイン情報からアカウントの存在確認をし、トークンを返します。

### Request Parameters

| Field       | Description                                | Example    | Remarks |
| :---------- | :----------------------------------------- | :--------- | :------ |
| `username`  | MinecraftID or MinecraftUUID (with hyphen) | `X4Z`      |         |
| `password`  | Password                                   | `xxxxx...` |         |
| `recaptcha` | Google reCAPTCHA Token                     |            |         |

### Response

[基本レスポンス](/api-docs/topics/basic-response)に加え、以下が返却されます。

| Field       | Description | Example                            | Remarks         |
| :---------- | :---------- | :--------------------------------- | :-------------- |
| `usertoken` | UserToken   | `XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX` | 32 桁、英数字。 |

### Remarks

- トークンは発行から 3 時間で無効になります。無効なキーが渡された場合、`401 Unauthorized`を返します。
- トークンが新規発行された場合、古いトークンは無効になります。古いトークンが渡された場合、`401 Unauthorized`を返します。

## Register

- **POST** `/club/register`

ユーザーキーからユーザー情報を取得し clubjaoafa へ新規登録したのち、トークンを返します。

### Request Parameters

| Field       | Description                                | Example    | Remarks |
| :---------- | :----------------------------------------- | :--------- | :------ |
| `username`  | MinecraftID or MinecraftUUID (with hyphen) | `X4Z`      |         |
| `password`  | Password                                   | `xxxxx...` |         |
| `recaptcha` | Google reCAPTCHA Token                     |            |         |

### Response

[基本レスポンス](/api-docs/topics/basic-response)に加え、以下が返却されます。

| Field       | Description | Example                            | Remarks         |
| :---------- | :---------- | :--------------------------------- | :-------------- |
| `usertoken` | UserToken   | `XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX` | 32 桁、英数字。 |
