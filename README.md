# OAuthLogin [![Build status](https://ci.appveyor.com/api/projects/status/i37i1sd16y31sa30?svg=true)](https://ci.appveyor.com/project/seven1986/oauthlogin-u3622) [![NuGet](https://img.shields.io/nuget/v/OAuthLogin.svg)](https://www.nuget.org/packages/OAuthLogin) [![GitHub license](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://raw.githubusercontent.com/seven1986/OAuthLogin/master/LICENSE)


Installation
-------------

OAuthLogin is available as a NuGet package. You can install it using the NuGet Package Console window:

```
PM> Install-Package OAuthLogin
```


Usage
------

��һ������Global.asax����΢����΢�š�QQ��facebook��client_id��client_secret

```csharp
protected void Application_Start(object sender, EventArgs e)
        {
            LoginProvider.UseFaceBook("client_id", "client_secret");

            LoginProvider.UseQQ("client_id", "client_secret");

            LoginProvider.UseWechat("client_id", "client_secret");

            LoginProvider.UseWeibo("client_id", "client_secret");
        }
```

�ڶ���������Ŀ��Ŀ¼�ֱ��½�QQ.aspx��Wechat.aspx��Webo.aspx��Facebook.aspx�ļ�

##### QQ.aspx

```csharp
 protected void Page_Load(object sender, EventArgs e)
        {
            var res = new QQ().Authorize();

            if (res != null && res.code == 0)
            {
                //�õ�������ݣ�Ȼ������Զ�����ת
                //res.result

            }
        }
```

##### Wechat.aspx

```csharp
protected void Page_Load(object sender, EventArgs e)
        {
            var res = new Wechat().Authorize();

            if (res != null && res.code == 0)
            {
                //�õ�������ݣ�Ȼ������Զ�����ת
                //res.result
            }
        }
```

##### Webo.aspx

```csharp
protected void Page_Load(object sender, EventArgs e)
        {
            var res = new Weibo().Authorize();

            if (res != null && res.code == 0)
            {
                //�õ�������ݣ�Ȼ������Զ�����ת
                //res.result
            }
        }
```

##### Facebook.aspx

```csharp
protected void Page_Load(object sender, EventArgs e)
        {
            var res = new Facebook().Authorize();

            if (res != null&& res.code==0)
            {
                //�õ�������ݣ�Ȼ������Զ�����ת
                //res.result
            }
        }
```