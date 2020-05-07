### Server SDK

_单元测试覆盖率:_

![](./report.png)

**文档迁移至**: http://www.rongcloud.cn/docs/server_sdk_api/

[SDK 功能清单](./function-list.md)

#### 初始化

1、生产环境 Node.js 支持最低版本为 [4.0+](http://nodejs.cn/download/)，开发环境要求 Node.js 最低版本为 [8.0+](http://nodejs.cn/download/)

2、安装 `rongcloud-sdk`

```
npm install rongcloud-sdk
```

#### 使用

请前往 [开发者后台](https://developer.rongcloud.cn) 创建应用 -> 获取 Appkey、Secret

以注册用户为例

**Promise 方式**

```js
//替换成您自己的 Appkey
var appkey = '8luwapucoil';
// 替换成您自己的 Secret
var secret = 'y0iyjl4h3LWz';

var RongSDK = require('rongcloud-sdk')({
    appkey: appkey,
    secret: secret
});

// API 文档: http://www.rongcloud.cn/docs/server/sdk/user/user.html#register
var User = RongSDK.User;
var user = {
	id: 'ujadk90ha',
	name: 'Maritn',
	portrait: 'http://7xogjk.com1.z0.glb.clouddn.com/IuDkFprSQ1493563384017406982'
};
User.register(user).then(result => {
	console.log(result);
}, error => {
	console.log(error);
});
```

**Co 方式**
```js
//替换成您自己的 Appkey
var appkey = '8luwapucoil';
// 替换成您自己的 Secret
var secret = 'y0iyjl4h3LWz';

var RongSDK = require('rongcloud-sdk')({
    appkey: appkey,
    secret: secret
});
var co = require('co');

// API 文档: http://www.rongcloud.cn/docs/server/sdk/user/user.html#register
var User = RongSDK.User;
co(function* (){
  var user = {
  	id: 'ujadk90ha',
  	name: 'Maritn',
  	portrait: 'http://7xogjk.com1.z0.glb.clouddn.com/IuDkFprSQ1493563384017406982'
  };
  var result = yield User.register(user)
  console.log(result);
}).catch(error => {
  console.log(error);
});
```

#### 文档

[API 文档](https://www.rongcloud.cn/docs/server_sdk_api/)

#### 示例

**[用户模块示例](./example/promise/user)**

**[消息模块示例](./example/promise/message)**

**[群组模块示例](./example/promise/group)**

**[聊天室模块示例](./example/promise/chatroom)**

**[会话模块示例](./example/promise/conversation.js)**

**[敏感词模块示例](./example/promise/sensitive.js)**

**[远程推送](./example/promise/push.js)**

#### 单元测试

1、下载或克隆 `server-sdk-nodejs`

2、进入项目 `cd server-sdk-nodejs`

3、安装依赖 `npm install`

4、运行单元测试 `npm test`

#### 声明

3.0.0 版本 SDK API 不再向老版本兼容，老版本 SDK 可用但不再维护
