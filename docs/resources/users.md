# Resources/Users

- [TopPage](/api-docs/)

jao Minecraft Server Minecraft サービスにログインしたことのある利用者の情報のみを取得できます。  
1.8.8 鯖(2018/02/17)以前のデータは含まず、1.12.2 鯖(2018/03/20)以降のデータのみを取得可能対象とします。

## Get User

- **GET** `/users`
- **GET** `/users/{minecraft.id}`
- **GET** `/users/{minecraft.uuid}`
- **GET** `/users/{discord.id}`

[ユーザオブジェクト](/api-docs/object/user)を返します。  
この API で返される Minecraft ID は最新でない可能性があることに注意してください。jao Minecraft Server の最終ログインの情報から取得されます。

### Request Parameters

このエンドポイントのパラメータはすべて Optional ですが、いずれかのパラメータがなければなりません。

| Field              | Description                  | Example                                | Remarks |
| :----------------- | :--------------------------- | :------------------------------------- | :------ |
| `{minecraft.uuid}` | Minecraft UUID (with hyphen) | `5799296a-d1ec-4252-93bd-440bb9caa65c` |         |
| `{discord.id}`     | Discord ID                   | `206692134991036416`                   |         |
| `mcid`             | Minecraft ID                 | `X4Z`                                  |         |
| `uuid`             | Minecraft UUID (with hyphen) | `5799296a-d1ec-4252-93bd-440bb9caa65c` |         |
| `discordid`        | Discord ID                   | `206692134991036416`                   |         |

### Response

[基本レスポンス](/api-docs/topics/basic-response)に加え、以下が返却されます。

| Field  | Description                                   | Example | Remarks |
| :----- | :-------------------------------------------- | :------ | :------ |
| `data` | [ユーザーオブジェクト](/api-docs/object/user) |         |         |

## Get MCBans user data

- **GET** `/users/mcbans`
- **GET** `/users/mcbans/{minecraft.uuid}`

[MCBans ユーザデータオブジェクト](/api-docs/object/user-mcbans)を返します。

### Request Parameters

このエンドポイントのパラメータはすべて Optional ですが、いずれかのパラメータがなければなりません。

| Field              | Description                  | Example                                | Remarks |
| :----------------- | :--------------------------- | :------------------------------------- | :------ |
| `{minecraft.uuid}` | Minecraft UUID (with hyphen) | `5799296a-d1ec-4252-93bd-440bb9caa65c` |         |
| `uuid`             | Minecraft UUID (with hyphen) | `5799296a-d1ec-4252-93bd-440bb9caa65c` |         |

### Response

[基本レスポンス](/api-docs/topics/basic-response)に加え、以下が返却されます。

| Field  | Description                                                     | Example | Remarks |
| :----- | :-------------------------------------------------------------- | :------ | :------ |
| `data` | [MCBans ユーザデータオブジェクト](/api-docs/object/user-mcbans) |         |         |

### Remarks

- jao Minecraft Server 側で定期的にデータを取得し記録しています。そのため、最新のデータでない可能性があります。
- 最新のデータを必要とする場合は MCBans の公式 API を利用してください。

## Get MCBans ban data

- **GET** `/users/mcbans/ban/{mcbans.banid}`

[MCBans Ban データオブジェクト](/api-docs/object/user-mcbans-ban)を返します。

### Request Parameters

| Field            | Description   | Example | Remarks |
| :--------------- | :------------ | :------ | :------ |
| `{mcbans.banid}` | MCBans Ban ID | `1`     |         |

### Response

[基本レスポンス](/api-docs/topics/basic-response)に加え、以下が返却されます。

| Field  | Description                                                       | Example | Remarks |
| :----- | :---------------------------------------------------------------- | :------ | :------ |
| `data` | [MCBans Ban データオブジェクト](/api-docs/object/user-mcbans-ban) |         |         |

### Remarks

- jao Minecraft Server 側で定期的にデータを取得し記録しています。そのため、最新のデータでない可能性があります。
- 最新のデータを必要とする場合は MCBans の公式 API を利用してください。

## jao Super Achievement2 getted achievements

- **GET** `/users/jsa/{minecraft.uuid}`

[jao Super Achievement2](https://github.com/jaoafa/jao-Super-Achievement2) の解除済み実績を配列([jSA 実績オブジェクト](/api-docs/object/jsa-achievement))として返します。

### Request Parameters

| Field              | Description                  | Example                                | Remarks |
| :----------------- | :--------------------------- | :------------------------------------- | :------ |
| `{minecraft.uuid}` | Minecraft UUID (with hyphen) | `5799296a-d1ec-4252-93bd-440bb9caa65c` |         |

### Response

[基本レスポンス](/api-docs/topics/basic-response)に加え、以下が返却されます。

| Field  | Description                                                     | Example | Remarks |
| :----- | :-------------------------------------------------------------- | :------ | :------ |
| `data` | [jSA 実績オブジェクト](/api-docs/object/jsa-achievement) の配列 |         |         |
