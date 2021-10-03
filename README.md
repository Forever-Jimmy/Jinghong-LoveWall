# Jinghong-LoveWall
精弘表白墙项目
是精弘网络技术部 试用期项目

# API

## [1] [用户注册] [POST]
URL: domain:port/api/register
#### 传入数据
```
{
    "email" : "node520@example.com", // 电子邮件地址
    "username" : "node520",  // 用户昵称
    "password" : "5AA765D61D8327DE"  // 用户密码，用MD5（16位大写）加密，样例所示为"password"加密后的密文
}
```

#### 返回数据
```
{
    "return_value": 0 // 表示用户注册成功
                    -1 // 表示用户已存在（电子邮件已经注册）
                    -2 // 表示服务器错误
                    -3 // 表示请求错误
}
```

## [2] [用户登录] [POST]
URL: domain:port/api/login
#### 传入数据

```
{
    "email" : "node520@example.com", // 电子邮件地址
    "password" : "5AA765D61D8327DE"  // 用户密码
}
```

#### 返回数据

```
{
    "return_value" : 0, // 登录成功
                     -1, // 用户不存在
                     -2, // 密码错误
                     -3, // 重复登录
                     -4, // 服务器错误
                     -5, // 重复登录
    "token" : "xxxx" // token 客户端保存，需要token时需要上传。如果登录失败，返回的token是空
}
```