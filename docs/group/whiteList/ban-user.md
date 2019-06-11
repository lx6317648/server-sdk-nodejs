## 群禁言用户白名单服务

### WhiteList.user.add(group){#add}

在群组被禁言状态下，如果需要某些用户可以发言时，可将此用户加入到群组禁言用户白名单中。群禁言用户白名单，只有群组被设置为全部禁言时才会生效。

`group` 参数的**属性说明**：

| 参数   	 |	类型		| 必填	| 说明 							|最低版本	|
| :----------|:--------	|:-----	|:------------------------------|:----- |
| id		  		| string 	| 	是 	| 群 Id	 | 3.0.0 |
|	members  |	array	|	是 	| 白名单成员列表 |3.0.0|

`members` 说明:

| 参数   	 		|	类型		| 必填	| 说明 							|最低版本	|
| :----------------	|:--------	|:-----	|:------------------------------|:----- |
| id		  		| string 	| 	是 	| 群成员 Id，每次最多不超过 20 个。	 | 3.0.0 |

##### 请求成功

```json
{
    "code": 200
}
```

### WhiteList.user.remove(group){#remove}

移除群禁言白名单用户

`group` 参数的**属性说明**：

| 参数   	 |	类型		| 必填	| 说明 							|最低版本	|
| :----------|:--------	|:-----	|:------------------------------|:----- |
| id		  		| string 	| 	是 	| 群 Id	 | 3.0.0 |
|	members  |	array	|	是 	| 白名单成员列表 |3.0.0|

`members` 说明:

| 参数   	 		|	类型		| 必填	| 说明 							|最低版本	|
| :----------------	|:--------	|:-----	|:------------------------------|:----- |
| id		  		| string 	| 	是 	| 群成员 Id，每次最多不超过 20 个。	 | 3.0.0 |

##### 请求成功

```json
{
    "code": 200
}
```

### WhiteList.user.getList(group){#getList}

查询群禁言白名单用户列表

`group` 参数的**属性说明**：

| 参数   	 		|	类型		| 必填	| 说明 							|最低版本	|
| :----------------	|:--------	|:-----	|:------------------------------|:----- |
| id		  		| string 	| 	是 	| 群 Id	 | 3.0.0 |

##### 请求成功

```json
{
	"code": 200,
	"members":[{
		"id":"2582"
	}]
}
```

| 参数   	 |	类型		| 说明
| :----------|:--------	|:-----
|	id		 |	string	| 成员 Id