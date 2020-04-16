# Topics/Basic-Response

- [TopPage](/api-docs/)

基本レスポンスは、すべての API のレスポンスに必ず組み込まれます。  
以下基本レスポンスに追加して各エンドポイント独自のレスポンスがマージされて返却されます。

| Field   | Description       | Example | Remarks                          |
| :------ | :---------------- | :------ | :------------------------------- |
| status  | Response status   | true    | 成功時は true が、失敗時は false |
| code    | HTTP status code  | 200     |                                  |
| version | API Minor Version |         | GitHub の Commit ID              |
