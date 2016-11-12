

# SREApiDOC

## 用户



### `POST`用户登陆

`/user/login`

INPUT

```json
{
  "email": "xingshunkai@qq.com",
  "password": ""
}
```



OUTPUT

```json

```





### `POST`用户注册

`/user/register`





### `GET`查询用户



根据user_id 查找用户

`/user？user_id = 12`

根据用户邮箱查找用户

`/user？email = "xing@qq.com"`





INPUT

```

```

OUTPUT

```
{
  "user_id": "12",
  "user_name"："Kyle", //用户昵称
  "user_avatar": "/path/to/user/avatar/url", // 用户头像
  "email":"K@qq.com"
}
```







### `GET`获取用户详细信息

前置条件： 已登陆



`/user/:user_id`





OUTPUT

```
TODO
```





### `GET`查询有项目经历的其他用户



`/user/:user_id/relationship`



OUTPUT

```json
[
  {
  "user_id": "12",
  "user_name"："Kyle", //用户昵称
  "user_avatar": "/path/to/user/avatar/url", // 用户头像
  "email":"K@qq.com"
},
{
  "user_id": "12",
  "user_name"："Kyle", //用户昵称
  "user_avatar": "/path/to/user/avatar/url", // 用户头像
  "email":"K@qq.com"
},
{
  "user_id": "12",
  "user_name"："Kyle", //用户昵称
  "user_avatar": "/path/to/user/avatar/url", // 用户头像
  "email":"K@qq.com"
}
]
```





## 项目



### `POST`创建项目 



`/project`

INPUT

```JSON
{
  "project_name": "软件需求管理开发工具",	// 项目名称
  "project_info":"软件需求工程开发工具，使用范围是。。。",	// 项目的说明
  "user_id":12,	//创建者
}
```

RETURN

Status: 200 ,OK

```json
{
	"project_id": 101,
	"project_name": "软件需求工程开发工具"
}
```



### `GET`获取项目列表



`/project？user_id=12`



INPUT

```

```



RETURN

```JSON
[
  {
    "project_id": 1,
    "project_name": "网易云音乐",
    "project_picture_url": "/path/to/project/logo/image",
    "role": 2 	// 该用户在项目中角色 {}
   }，
  {
    "project_id": 1,
    "project_name": "网易云音乐",
    "project_picture_url": "/path/to/project/logo/image",
    "role": 2 	// 该用户在项目中角色 {}
  }  
]
```





### `GET`查看团队成员



`project/:project_id/member`

INPUT

```

```



OUTPUT

```json
[
  {
  "user_id": "12",
  "user_name"："Kyle", //用户昵称
  "user_avatar": "/path/to/user/avatar/url", // 用户头像
  "email":"K@qq.com",
  "role": 1 // 在项目中的角色
}，
{
  "user_id": "12",
  "user_name"："Kyle", //用户昵称
  "user_avatar": "/path/to/user/avatar/url", // 用户头像
  "email":"K@qq.com"，
    "role": 1 // 在项目中的角色
}，
{
  "user_id": "12",
  "user_name"："Kyle", //用户昵称
  "user_avatar": "/path/to/user/avatar/url", // 用户头像
  "email":"K@qq.com"，
    "role": 1 // 在项目中的角色
}
]
```





### `POST`添加团队成员



`project/:project_id/member`



INPUT

```JSON
{
  // 平台内的用户，发送邀请信息
  "UsersList":[
    {
      "user_id": 12,
      "role": 2
    },{
      "user_id": 13,
      "role": 3
    }
  ],
  // 平台外的用户 - Email 邀请
  "PotentialUserList":[
    {
      "email":"xing@qq.com"，
      "role": 2
    },
    {
      "email":"xing@qq.com",
      "role": 2
    }
  ]
}
```





## 文档

### `GET`  获取文档列表（根据文件夹分组）



### `GET` 获取文档 - 发布版





### `GET` 获取文档 - 编辑版





### `GET` 获取文档所有的编辑历史





### `GET` 获取文档所有的发布版的历史







### `POST`创建文档





### `POST`添加版本和版本说明





### `PUT`更新文档

> Note : 更新文档时,每次更新创建一个Article
>
> 然后更新 Document的ArticleEditId



### `DLETE` 删除文档

