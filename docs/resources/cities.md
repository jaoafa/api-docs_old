# Resources/Cities

- [TopPage](/api-docs/)

jao Minecraft Server Minecraft サービスにおいて運営によって認可され、登録された自治体の情報を取得・編集できます。

## Get City

- **GET** `/cities`
- **GET** `/cities/{cities.id}`

[自治体オブジェクト](/api-docs/object/city)を返します。

### Request Parameters

このエンドポイントのパラメータはすべて Optional ですが、いずれかのパラメータがなければなりません。

| Field         | Description | Example | Remarks |
| :------------ | :---------- | :------ | :------ |
| `{cities.id}` | 自治体 ID   | `1`     |         |
| `id`          | 自治体 ID   | `1`     |         |
| `name`        | 自治体名    | 爆新地  |         |

### Response

| Field    | Description                                 | Example | Remarks                                                                         |
| :------- | :------------------------------------------ | :------ | :------------------------------------------------------------------------------ |
| `status` | Request status (boolean)                    | `true`  | false の場合、[エラーレスポンス](/api-docs/topics/error-response)が使用されます |
| `data`   | [自治体オブジェクト](/api-docs/object/city) |         |                                                                                 |

## Create City (Request)

新規自治体登録のリクエストをします。

- **POST** `/cities/create`

### Request Parameters

| Field              | Description              | Example                                                                                                 | Remarks               |
| :----------------- | :----------------------- | :------------------------------------------------------------------------------------------------------ | :-------------------- |
| `verificationCode` | 認証コード               | `XXXXXXXXXX`                                                                                            | 10 桁、アルファベット |
| `cityName`         | 自治体名                 | `爆新地`                                                                                                |                       |
| `cityNameKana`     | 自治体名読み             | `ばくしんち`                                                                                            |
| `summary`          | 自治体名概要             | `Jao_Afaワールドの中心に位置する運営が管理する自治体`                                                   |                       |
| `origin`           | 自治体名由来             | `爆発の始まり。爆発の根源。中心地。つまり爆心地。新しいので爆新地。`                                    |                       |
| `region`           | 入力範囲情報             | `[{"id":1,"x":"0","z":"0"},{"id":2,"x":"0","z":"0"},{"id":3,"x":"0","z":"0"},{"id":4,"x":"0","z":"0"}]` | Array                 |
| `count`            | ブロック数               | `1048576`                                                                                               |                       |
| `reason`           | 規定ブロックを超える理由 |                                                                                                         |
| `remarks`          | 備考                     |                                                                                                         |

### Response

| Field    | Description              | Example | Remarks                                                                         |
| :------- | :----------------------- | :------ | :------------------------------------------------------------------------------ |
| `status` | Request status (boolean) | `true`  | false の場合、[エラーレスポンス](/api-docs/topics/error-response)が使用されます |

## Approval City Request

- **POST** `/cities/approval/{request.type}/{cities.id}`

自治体のリクエストを承認し、反映します。

### Request Parameters

| Field          | Description    | Example  | Remarks                                                   |
| :------------- | :------------- | :------- | :-------------------------------------------------------- |
| `request.type` | リクエスト種別 | `create` | `create` = 新規, `region` = 範囲変更, `update` = 情報更新 |
| `cities.id`    | 自治体 ID      | 1        |                                                           |

## Response

| Field    | Description              | Example | Remarks                                                                         |
| :------- | :----------------------- | :------ | :------------------------------------------------------------------------------ |
| `status` | Request status (boolean) | `true`  | false の場合、[エラーレスポンス](/api-docs/topics/error-response)が使用されます |

## Reject City Request

- **POST** `/cities/reject`

自治体のリクエストを否認します。

### Request Parameters

| Field            | Description    | Example  | Remarks                                                   |
| :--------------- | :------------- | :------- | :-------------------------------------------------------- |
| `{request.type}` | リクエスト種別 | `create` | `create` = 新規, `region` = 範囲変更, `update` = 情報更新 |
| `{cities.id}`    | 自治体 ID      | 1        |                                                           |

## Response

| Field    | Description              | Example | Remarks                                                                         |
| :------- | :----------------------- | :------ | :------------------------------------------------------------------------------ |
| `status` | Request status (boolean) | `true`  | false の場合、[エラーレスポンス](/api-docs/topics/error-response)が使用されます |

## Update City

- **PUT** `/cities/{cities.id}`

自治体情報を更新します。

## Delete City

- **DELETE** `/cities/{cities.id}`

自治体情報を削除します。
