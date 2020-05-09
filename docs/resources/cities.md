# Resources/Cities

- [TopPage](/api-docs/)

jao Minecraft Server Minecraft サービスにおいて運営によって認可され、登録された自治体の情報を取得・編集できます。

## Get City

- **GET** `/cities`
- **GET** `/cities/{cities.id}`
- **GET** `/cities/{cities.owner.uuid}`

[自治体オブジェクト](/api-docs/object/city)を返します。

### Request Parameters

このエンドポイントのパラメータはすべて Optional です。

| Field                 | Description       | Example                                | Remarks |
| :-------------------- | :---------------- | :------------------------------------- | :------ |
| `{cities.id}`         | 自治体 ID         | `1`                                    |         |
| `{cities.owner.uuid}` | 自治体管理者 UUID | `5799296a-d1ec-4252-93bd-440bb9caa65c` |         |
| `id`                  | 自治体 ID         | `1`                                    |         |
| `name`                | 自治体名          | 爆新地                                 |         |

### Response

[基本レスポンス](/api-docs/topics/basic-response)に加え、以下が返却されます。

| Field  | Description                                 | Example | Remarks |
| :----- | :------------------------------------------ | :------ | :------ |
| `data` | [自治体オブジェクト](/api-docs/object/city) |         |         |

パラメーターが指定されていない場合、全ての登録自治体の自治体オブジェクトを配列として返します。

## Create City (Request)

新規自治体登録のリクエストをします。

- **POST** `/cities/create`

### Request Parameters

| Field          | Description                 | Example                                                                                                 | Remarks                                                                                                                |
| :------------- | :-------------------------- | :------------------------------------------------------------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------- |
| `usertoken`    | UserToken                   | `XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX`                                                                      | 32 桁、英数字。                                                                                                        |
| `cityName`     | 自治体名                    | `爆新地`                                                                                                |                                                                                                                        |
| `cityNameKana` | 自治体名読み                | `ばくしんち`                                                                                            |
| `summary`      | 自治体名概要                | `Jao_Afaワールドの中心に位置する運営が管理する自治体`                                                   |                                                                                                                        |
| `origin`       | 自治体名由来                | `爆発の始まり。爆発の根源。中心地。つまり爆心地。新しいので爆新地。`                                    |                                                                                                                        |
| `corners`      | 入力範囲情報                | `[{"id":1,"x":"0","z":"0"},{"id":2,"x":"0","z":"0"},{"id":3,"x":"0","z":"0"},{"id":4,"x":"0","z":"0"}]` | Array                                                                                                                  |
| `count`        | ブロック数                  | `1048576`                                                                                               |                                                                                                                        |
| `reason`       | 規定ブロックを超える理由    |                                                                                                         |
| `remarks`      | 備考                        |                                                                                                         |
| `recaptcha`    | Google Recaptcha のトークン |                                                                                                         |                                                                                                                        |
| `force`        | 強制的に追加するか          | `false`                                                                                                 | この引数を`true`にするには apikey パラメータが必要です。`true`にするとこの申請を即時に承認されたものとして登録します。 |
| `apikey`       | API Key                     |                                                                                                         | 開発部が発行する`apikey`のみ。基本的に運営のみに発行します。                                                           |

### Response

[基本レスポンス](/api-docs/topics/basic-response)が返却されます。

### Remarks

- 認証コードは [jaoafa/MyMaid3](https://github.com/jaoafa/MyMaid3) に実装されている `/getuserkey` コマンドにて取得できます。
- この API で使用された認証コードはリクエスト後に「使用済み」として無効化され、他の API で再利用することができない点を注意してください。無効化後、再取得することで有効な認証コードが払い出されます。
- 自治体名称、自治体名称読みのいずれかがが既存の自治体と同じ場合エラーとなります。(409 conflict を返します)
- 利用者情報は認証コードから取得します。自治体管理者はこの利用者情報より設定します。

## Approval City Request

- **POST** `/cities/approval/{request.type}/{cities.id}`

自治体のリクエストを承認し、反映します。

### Request Parameters

| Field          | Description    | Example  | Remarks                                                      |
| :------------- | :------------- | :------- | :----------------------------------------------------------- |
| `request.type` | リクエスト種別 | `create` | `create` = 新規, `region` = 範囲変更, `update` = 情報更新    |
| `cities.id`    | 自治体 ID      | 1        |                                                              |
| `apikey`       | API Key        |          | 開発部が発行する`apikey`のみ。基本的に運営のみに発行します。 |

## Response

[基本レスポンス](/api-docs/topics/basic-response)が返却されます。

## Reject City Request

- **POST** `/cities/reject/{request.type}/{request.id}`

自治体のリクエストを否認します。

### Request Parameters

| Field            | Description    | Example  | Remarks                                                   |
| :--------------- | :------------- | :------- | :-------------------------------------------------------- |
| `{request.type}` | リクエスト種別 | `create` | `create` = 新規, `region` = 範囲変更, `update` = 情報更新 |
| `{cities.id}`    | 自治体 ID      | 1        |                                                           |

### Response

[基本レスポンス](/api-docs/topics/basic-response)が返却されます。

## Update City

- **PATCH** `/cities/edit/{cities.id}`

自治体情報を更新します。

### Request Parameters

`{cities.id}`と`usertoken`、`recaptcha`以外のパラメーターは全て Optional です。指定されたパラメーターの項目のみを更新します。

| Field          | Description                 | Example                                                                                                 | Remarks         |
| :------------- | :-------------------------- | :------------------------------------------------------------------------------------------------------ | :-------------- |
| `{cities.id}`  | 自治体 ID                   | 1                                                                                                       |                 |
| `usertoken`    | UserToken                   | `XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX`                                                                      | 32 桁、英数字。 |
| `cityName`     | 自治体名                    | `爆新地`                                                                                                |                 |
| `cityNameKana` | 自治体名読み                | `ばくしんち`                                                                                            |
| `summary`      | 自治体名概要                | `Jao_Afaワールドの中心に位置する運営が管理する自治体`                                                   |                 |
| `origin`       | 自治体名由来                | `爆発の始まり。爆発の根源。中心地。つまり爆心地。新しいので爆新地。`                                    |                 |
| `corners`      | 入力範囲情報                | `[{"id":1,"x":"0","z":"0"},{"id":2,"x":"0","z":"0"},{"id":3,"x":"0","z":"0"},{"id":4,"x":"0","z":"0"}]` | Array           |
| `count`        | ブロック数                  | `1048576`                                                                                               |                 |
| `reason`       | 規定ブロックを超える理由    |                                                                                                         |
| `remarks`      | 備考                        |                                                                                                         |
| `recaptcha`    | Google Recaptcha のトークン |                                                                                                         |                 |

### Response

[基本レスポンス](/api-docs/topics/basic-response)が返却されます。

### Remarks

- `usertoken` から取得される利用者情報と自治体情報の管理者が合致しない場合、 `403 Forbidden` が返却されます。
- **申請形式上の問題により、`corners` 変更時は他の情報と一緒に更新することはできません。**
- `clubgroup` ([clubjaoafa アカウントオブジェクト](/api-docs/object/club-account)参照) が`admin`の場合、すべての自治体の情報を更新できます。この場合、申請という形式ではなく強制更新扱いとなります。
  - なお、`admin` であっても自身の自治体情報を更新する場合は申請という形式で一般利用者同様に処理されます。

## Delete City

- **DELETE** `/cities/{cities.id}`

自治体情報を削除します。
